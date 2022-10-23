# Foodie Boogies

23 Oct 2022

PLEASE NOTE:
The deployed version fails to show the contents of the category products page in the narrow/mobile display. The intended responsive layouts should work fine through VSCode's debug demo and can the website be tested there. This problem was found too late to be fixed before the deadline, as issues were not expected in the deployment stage.

## Description

Foodie Boogies is a Dart/Flutter web app portraying an online store for groceries. The store provides supplies in five product categories: Fruit and Vegetables, Grains, Sweets, Snacks, and Drinks. The user can browse and search for products and product categories, add products to cart, adjust the amount of each product type in cart, select their method of payment, and confirm their order. They can also adjust their personal user settings like name, address, and credit card number, which are stored and remembered also after refreshing the website.

### Application functionality
--------

When the web app is first started, the user starts from a landing page presenting the store's product categories and some of the store's supplied products. Via the icon buttons in the navigation bar, the user can also select to view or edit their user settings or look at their shopping cart, whose product count (initally 0) is shown below the button. Using the navigation buttons below the short website description, the user can navigate to the page listing the categories or to the search page.

There are multiple levels to browsing the store's products: on the category list page, the user can see all the available categories depicted by the category name and an image of an example product. If a category is clicked on (either on the landing page or on the category list page), the user is taken to the category's own page where all the category products are shown with their names, images, and prices. If a product card/tile is clicked on, a product page is opened, where the product can be added to the shopping cart, changing the number displayed on the top app bar.

If the user wants to view their current cart, they can click on the cart icon and open the cart page. There the current added products are listed, showing the image, name, and price of a piece. The sum cost of added products is shown for each product individually and for the whole cart, too. The user can increment or decrement the amount of product pieces with the + and - buttons given for each product. Once the user is pleased with their order, they can proceed to select their preferred method of payment on another page. There, three options are provided: Bank account, MobilePay, and Credit Card - which can be changed via this page or also the user settings page. A preview of the order is still shown along with the payment method selection. Then, the user can either return to the cart (or browsing the products) or confirm their payment, taking them to the order confirmation page that shows the final recap of the order.

The user settings page is accessed via the top app bar's user icon button. There, the user can view and edit their personal settings, which are null by default. The information that the user can provide are their name, (home) address, and credit card number. The saved settings are remembered throughout website refreshes. 

The website is responsive, catering for up to 3-4 different display sizes (depending on the viewed page). The pages that list either products, categories, or both have the options displayed as cards in scrollable grids in the wider layouts (2 columns for >600px, 3 columns for >1000px); for the mobile layouts (<600px), the cards are in a more compact list formation. On the Categories list / All categories page, there is also a fourth breakpoint (>1200px) that lets the user click on a category card on the left hand size, which opens a list of the category's products on the right. This list's items can be clicked to directly open the product page.

The product images used on this website are open source (licence: CC0 1.0) and can be found at
[https://iconduck.com/sets/food-icons](https://iconduck.com/sets/food-icons).

### Deployment
--------

Foodie Boogies is deployed and can be accessed at  
[https://katkalliok.github.io/foodie-boogies/](https://katkalliok.github.io/foodie-boogies/).

(I hope that my fellow peers have the mercy and patience to mostly base their reviews on the non-deployed debug performance where everything works rather than the deployed one where almost everything works.)

## Development Process
  
### Key Challenges
---------

Here are some of the challenges I faced during the development process:

* **How to make the App Bar a reusable widget?** During the specifically panicky early stages of development, this was something I decided I had to time to look into. I briefly tried to make a separate widget file, but accessing it for the Scaffolds seemed confusingly unapproachable.
* **Mysterious oveflows, whitespaces, and alignments.** This project truly showed off the quirks of combining different widgets and its consequences. There is plenty of logic in this area that I simply could not understand or find out through googling, but most of the issues were luckily fixed by doing, well, just something.
* **Completely absurd provider state changes.** This is not a bitter exaggeration. Why would clicking on + button for one product simultaneously increase another product's amount by multiple pieces and decrease the amount of intended product? After countless desperate attempts of finding out, the mystery remained and a workaround had to be performed. Still, some issues may appear in this website version, since the logic of my StateNotifiers was not discovered and probably never will.

### Key Learning Moments
--------

Here are some of my memorable learning moments for this project:

* * **Understanding Gridview logic.** This was a tough learning process at the early stages of the project. These widgets are complex and needed familiarizing before I could decently handle them.
* **Differences of SharedPreferences and Providers.** The course assignments alone apparently were not enough to help me understand the logic and use of these different kinds of rememberers. Through some painful work, this project helped find some clarity in this regard.
* **When to use ConsumerWidget, ConsumerStatefulWidget, and StatefulWidget?** The differences of these were also a little unclear, and frankly still are. However, some progress was made through practice.
* **Flutter does not support SVGs.** This, too, was learned through pain, after manually uploading all 19ish images as SVGs first.
* **Do not .map, .forEach instead.** I already encountered this curious issue in my previous project, but I was amused by it once again. Somehow everything fell apart every time I mapped a list, and changing to forEach (which funnily enough was recommended to stay away from by the editor) saved the day many times (e.g. when using getOccurrences to fetch the cart products).
