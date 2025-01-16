1. Define Technical Requirements 

● Frontend Requirements:

• Interface should be user friendly for browsing products and so that it's easier for user to navigate to useful pages easily, Website's landing page should me minimal and clean and with a clear call to action button from where user can easily navigate to products listing page.

• Design should be made with mobile first approach since most user traffic is generated from mobile phones nowadays; It should be minimal so that user doesn't get distracted, and it should be responsive for all the devices from mobile phone to desktop.

• Some of the essentials pages of my marketplace are: 

1. Home Page / Landing Page: with clean hero section with a call to action button that sends user to product listing page where he can browse variety of products.

2. Product Listing page: On product lisiting page user can click on any product to navigate to that product details page.

3. Product Details page: 

In product details page user will find clean and minimal UI so that it doesn't distract him from the main goal, which is purchasing product.

• Product Information:

Display product details (name, description, price, and image).
Ensure a visually appealing and distraction-free design.

• Color Selection:

Include several buttons representing available colors for the product.
When a color is selected, dynamically display size options available for that color.

• Size Selection:

Display size options as buttons beneath the color selection.
Sizes update dynamically based on the selected color.
Each size shows the stock availabe for that size.

• Quantity Update Buttons:

Displays two buttons with increment and decrement functionality showing the current quantity update between these buttons in a sandwich format.

• Add to Cart Button:

A single prominent button with the text "Add to Cart".

If the user hasn’t selected a color or size, display a Toast prompting the user to select these options.
On successful addition, display a Toast with the message {product.name} added to cart!.

• Under Product's Details:

There is a Section named "You Might Also Like" displaying various simillar products in a carousel.

Then There is a "What Makes Us Different" section with some high light of waht makes us different.

Then Finally there is a "Sign up for a Neesletter" section with email input and a "Sign Up" Button.


4. Cart page:

Cart Items displayed in table's with "remove from cart button" in table for each cart Item.

Under Cart Items There is a section justified-between with "Clear Cart button" and navigation to "Checkout". 

5. Checkout page:

If the customer is not signed-In he will be re directed to sign-in page, because we will be storing orders in sanity CMS, with refrence to clerkId, which is a unique userId provided by clerk, for every user.

In checkout page there is a form on left side where customer will fill his details like name, email. And on the right side there is a display of cart items in "In Your Cart" section with total amount and clear cart button.
This section is sticky so it scrolls down when user go through the form filling his details.

Right now I've set an Accordian with "Bank Transfer Details". 
Later I will remove it when payment gateway is integrated.

Finally on successfull Order placement confetti showers. 


6. Orders page:

Orders page will list customers previous order, with order status. and real-time tracking.