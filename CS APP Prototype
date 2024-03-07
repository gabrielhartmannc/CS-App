from IPython.display import Image, display
import requests
from io import BytesIO

def display_image_from_url(url):
    # Display an image from a URL
    display(Image(url=url))

def get_customer_choice(clothing_options):
    print("Please choose an article of clothing by entering the number:")
    for index, item in enumerate(clothing_options, start=1):
        print(f"{index}. {item}")
    choice = int(input("Enter your choice (number): ")) - 1
    chosen_item = list(clothing_options.keys())[choice]
    return chosen_item

def recommend_matching_clothes(chosen_clothing, recommendations):
    for recommendation in recommendations[chosen_clothing]:
        print(f"Recommended matching item: {recommendation['name']}")
        display_image_from_url(recommendation['url'])
        
        # Placeholder for customer feedback
        like_it = input("Do you like it? (yes/no): ").lower()
        if like_it == 'yes':
            return recommendation
    return None

def display_final_choice(chosen_clothing, matching_clothing):
    print(f"Your final choice:\nShirt: {chosen_clothing}")
    display_image_from_url(clothing_options[chosen_clothing])
    
    print(f"Pants: {matching_clothing['name']}")
    display_image_from_url(matching_clothing['url'])

# URLs to the uploaded images
clothing_options = {
    "Shirt 1": "https://www.dropbox.com/scl/fi/zgy52k61cd93bx8qhlv30/cn54312498.jpg.avif?rlkey=zqzoi0i452sg756mwqv8ilcps&dl=1" # Changed dl=0 to dl=1 for direct access
}

recommendations = {
    "Shirt 1": [
        {"name": "Pants 1", "url": "https://www.dropbox.com/scl/fi/vwtde6jc5tirj1m5gvmuk/e8d6df0e-1f91-42b6-a2f4-b48f82656645.lg.png?rlkey=a7nha5rro0860ele1zhesrxee&dl=1"}
        # Add more pants options here if you have them
    ]
}

# Main application logic
chosen_clothing = get_customer_choice(clothing_options)
matching_clothing = recommend_matching_clothes(chosen_clothing, recommendations)

if matching_clothing:
    display_final_choice(chosen_clothing, matching_clothing)
else:
    print("No matching clothing was selected.")
