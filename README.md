# add-to-cart-feature-vanilla

[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/vitejs-vite-iqjfvz)

This JavaScript code demonstrates how to build an "add to cart" feature for a fake e-commerce website using the Rick and Morty API. The code can be divided into several parts, which will be explained one by one.

DOM element selection: The script starts by selecting necessary elements from the DOM using querySelector. These elements include the list container, toggle and close cart buttons, cart list element, total items and price elements, cart section, and clear cart button. These elements are stored in variables and will be used later in the code to manipulate the webpage. Learn more about DOM manipulation here: [Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

Cart initialization: The cartList variable is initialized by retrieving the cart list from the local storage using JSON.parse(localStorage.getItem("cart_list")), which converts the JSON string back into a JavaScript object. If the cart list doesn't exist, an empty array is created with || []. The characters array is also initialized as an empty array. Learn more about local storage here: [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)

Event listeners: Event listeners are added to the toggle cart button, close cart button, and clear cart button. The first two event listeners open and close the cart by toggling and removing the "is-open" class on the cart section element, respectively. The third event listener is attached to the clear cart button and calls the clearCart function when clicked. Learn more about event listeners here: [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)

Fetching characters: The fetchCharacters function is called to fetch character data from the Rick and Morty API. This function uses the fetch() method to make an API request, and the response.json() method to parse the JSON response. The function then resets the HTML content of the listContainer and assigns the API results to the characters array. Learn more about fetch here: [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

Creating character cards: The fetchCharacters function loops through the characters array using forEach, and for each character, it calls the createCharacterCardHtml function, which returns an HTML string representing the character card. The HTML string is then added to the listContainer. Learn more about template literals here: [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)

Adding "Add to cart" buttons: After fetching the characters and creating the cards, the script selects all the "add to cart" buttons using querySelectorAll("[data-item]") and adds a click event listener to each button. When a button is clicked, the addToCart function is called with the button as its argument.

Adding items to the cart: The addToCart function retrieves the character ID from the button's data-item attribute, finds the character using getCharacterById(), and adds the character to the cartList array. The cart list in local storage is then updated using localStorage.setItem("cart_list", JSON.stringify(cartList)).

Updating the cart: The updateCart function is called after adding a character to the cart. This function loops through the cartList array and generates the HTML for each item in the cart using the createCartItemHTML function. It also calculates the total items and total price, and updates their respective HTML elements.

Clearing the cart: The clearCart function is called when the user clicks the clear cart button. It removes the cart list from local storage, resets the cartList array to an empty array, and calls the updateCart function to update the webpage.

Overall, the "add to cart" feature is achieved by fetching character data from an API, creating character cards with "add to cart" buttons, handling click events to add characters to the cart, updating the cart content, and providing the option to clear the cart. Each function plays a vital role in making this feature work seamlessly.
