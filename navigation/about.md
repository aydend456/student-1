---
layout: minima
title: About
permalink: /about/
comments: true
---

## As a conversation Starter
Some Videogames I play:
-Roblox
-Fortnite

Some Animes I Watch:
-One piece
-Solo Leveling
-Dragon Ball
-Jujutsu Kaisen

My Two Favorite Quotes:
"I can accept failure, everyone fails at something. But I can't accept not trying"- Micheal Jordan and "If you do the work, you get rewarded. There are no shortcuts in life."- Micheal Jordan

## Here are some places I have lived.

<comment>
Flags are made using Wikipedia images
</comment>

<style>
    /* Style looks pretty compact, 
       - grid-container and grid-item are referenced the code 
    */
    .grid-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
        gap: 10px;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item img {
        width: 100%;
        height: 100px; /* Fixed height for uniformity */
        object-fit: contain; /* Ensure the image fits within the fixed height */
    }
    .grid-item p {
        margin: 5px 0; /* Add some margin for spacing */
    }

    /* Food image styling for the favorite foods grid */
    .food-img {
        width: 100%;
        height: 100px;
        object-fit: cover;
        border-radius: 4px;
        display: block;
        margin-bottom: 8px;
    }

    .image-gallery {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
        gap: 10px;
        }

    .image-gallery img {
        max-height: 150px;
        object-fit: cover;
        border-radius: 5px;
    }
</style>

<!-- This grid_container class is used by CSS styling and the id is used by JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
    var living_in_the_world = [
        {"flag": "0/01/Flag_of_California.svg", "greeting": "Hey", "description": "California - forever"},
    ];

    // 3a. Consider how to update style count for size of container
    // The grid-template-columns has been defined as dynamic with auto-fill and minmax

    // 3b. Build grid items inside of our container for each row of data
    for (const location of living_in_the_world) {
        // Create a "div" with "class grid-item" for each row
        var gridItem = document.createElement("div");
        gridItem.className = "grid-item";  // This class name connects the gridItem to the CSS style elements
        // Add "img" HTML tag for the flag
        var img = document.createElement("img");
        img.src = http_source + location.flag; // concatenate the source and flag
        img.alt = location.flag + " Flag"; // add alt text for accessibility

        // Add "p" HTML tag for the description
        var description = document.createElement("p");
        description.textContent = location.description; // extract the description

        // Add "p" HTML tag for the greeting
        var greeting = document.createElement("p");
        greeting.textContent = location.greeting;  // extract the greeting

        // Append img and p HTML tags to the grid item DIV
        gridItem.appendChild(img);
        gridItem.appendChild(description);
        gridItem.appendChild(greeting);

        // Append the grid item DIV to the container DIV
        container.appendChild(gridItem);
    }
</script>

## Here are my favorite foods

<div class="grid-container2" id="grid_food">
    <!-- favorite food items will be added here by JavaScript -->
</div>

<script>
// Populate the Favorite Foods grid separately from the flags grid
(function(){
    const container = document.getElementById('grid_food');
    if (!container) return; // nothing to do if placeholder missing

    // Apply styles (grid layout is also defined in the top CSS, this reinforces it)
    container.style.border = '2px dashed';
    container.style.padding = '10px';
    container.style.display = 'grid';
    container.style.gridTemplateColumns = 'repeat(auto-fill, minmax(150px, 1fr))';
    container.style.gap = '10px';

    // Clear existing children to avoid duplicates when reloading
    container.innerHTML = '';

         // Example favorite foods with optional image paths (replace with your actual favorites and image files)
         const foods = [
             {name: 'Pizza', img: 'a/a3/Eq_it-na_pizza-margherita_sep2005_sml.jpg'},
             {name: 'Sushi', img: '1/1c/Colorful_sushi_lunch.jpg'},
             {name: 'Burgers', img: 'f/ff/In-N-Out_Burger_cheeseburgers_and_fries.jpg'},
             {name: 'Ice Cream', img: '6/6f/An_ice_cream_cone_at_a_Ben_%26_Jerry%27s_shop_in_Montreal.jpg'},
             {name: 'Tacos', img: '7/73/001_Tacos_de_carnitas%2C_carne_asada_y_al_pastor.jpg'},
             {name: 'Ramen', img: '5/56/Soy_Milk_Ramen_and_Tonkotsu_Miso_Ramen_by_Goemon_Ramen_Bar.jpg'},
         ];

         foods.forEach(food => {
                 const item = document.createElement('div');
                 item.className = 'grid-item';
                 item.style.padding = '12px';
                 item.style.textAlign = 'center';
                 item.style.borderRadius = '8px';
                 item.style.border = '1px solid';

                 // Image spot (if the file exists it will show; otherwise you'll see a broken image or can replace with a placeholder)
                 const img = document.createElement('img');
                 img.className = 'food-img';
                 img.src = food.img;
                 img.alt = food.name;
                 item.appendChild(img);

                 // Caption / name
                 const caption = document.createElement('p');
                 caption.textContent = food.name;
                 item.appendChild(caption);

                 container.appendChild(item);
         });
})();
</script>
</script>

<!-- Favorite TV Shows grid -->
Favorite TV Shows
<div class="grid-container3" id="shows_grid">
    <!-- Favorite shows will be added here by JavaScript -->
</div>

<script>
    // Base path for local images (place your images in /images/fav_shows/)
    var site_base = "{{ site.baseurl | default: '' }}";
    var shows_http_source = (site_base && site_base !== '')
        ? (site_base.replace(//$/, '') + '/images/fav_shows/')
        : './images/fav_shows/';
    var favorite_shows = [
        {"img": "3/34/One_piece_logo_1.svg", "title": "One-Piece"},
        {"img": "9/9b/Dragon_Ball_Z_Logo.png", "title": "DragonBall-Z"},
        {"img": "f/f4/Solo_Leveling_logo.svg", "title": "Solo-Leveling"},
        {"img": "6/6a/Jujutsu_Kaisen_logo_in_Japan.png", "title": "Jujutsu-Kaisen"}
    ];

    var showsContainer = document.getElementById("shows_grid");
    for (const show of favorite_shows) {
        var item = document.createElement("div");
        item.className = "grid-item";
        var img = document.createElement("img");
        img.src = shows_http_source + encodeURIComponent(show.img);
        img.alt = show.title;
        var p = document.createElement("p");
        p.textContent = show.title;
        item.appendChild(img);
        item.appendChild(p);
        showsContainer.appendChild(item);
    }
</script>
### Journey through Life

Here is what I did at those places

-I was born here in California in 2010 and stayed here my whole life
-🏫 I went to Hiltop Elementary school in 2015 since they had a preschool there and stayed until 2022
-🏫 I moved over here to 4s Ranch and went to Oak Valley Middle School in 2022, graduated in 2024
-👨‍🏫 I then came to Del Norte High School in 2024 and ever since then the story continues until I graduate in 2028

### Culture, Family, and Fun

I am super close with my family especially my mom.
My family has definitely a big inspiration in my life and encourages me to better myself everyday.
I love spending time with my family and go on vacations with them.

<comment>
Gallery of Pics:
</comment>
<div class="image-gallery">
<img src="aydend456/student/images/tokyo-tower.jpg" alt="Image 1">
<img src="aydend456/student/images/my-mom-and-I.jpg" alt="Image 2">
<img src="aydend456/student/images/ayden.jpg" alt="Image 3">
</div>