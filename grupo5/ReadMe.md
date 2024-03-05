## Link al Repositorio: https://github.com/cuadriante/P1SOA_MY_SERVICE/

## API INPUTS

To utilize the API correctly, users should utilize the "Get Recommendation" request, which requires three inputs: "input," "recommendation_of," and "recommendation_type."

* Meal 

The "meal" parameter represents the components of a meal. It is composed of “main_dish”, "drink", and "dessert". 

Error code 400 will be returned if meal parameter was not introduced or doesn't follow Meal structure.

* Recommendation_Of

The "recommendation_of" parameter specifies what the user wants to be recommended based on the remaining components of the dish. This should be the other remaining component(s) that were not included in the "input" parameter. For instance, if the user specifies the main dish in the "input," then "recommendation_of" could be set to either dessert or drink.

Error code 400 will be returned if recommendation_of parameter was not introduced or invalid recommendation_of data was provided.

* Src (source)

Lastly, the "src" parameter determines the source of where the recommendation will come from. There are three options:
> * LOCALDB: Uses a local database with predefined menu and recommendations.
> * OPENAI: Uses the openai api to utilize AI-based recommendations.
> * EXTERNAL: Uses external endpoints to get the recommendation. 

By providing these inputs correctly, users can tailor their requests and receive relevant recommendations based on their preferences.

## API OUTPUT

The recommendation message is generated in response to the input provided by the user and the desired recommendation target. For example, if the user requests a recommendation for the dessert component based on the main dish they have selected, the output message will specify the recommended dessert option. Similarly, if the user opts for recommendations based on an AI model or an external endpoint, the output message will reflect the recommended item sourced from these sources accordingly.

## FOOD IN AVAIBLE FOR RECOMMENDATIONS
```json
[
        "main_dish" : "pizza",
        "drink" : "coke",
        "dessert" : "ice cream"
        "main_dish" : "salad",
        "drink" : "smoothie",
        "dessert" : "watermelon"
        "main_dish" : "chicken",
        "drink" : "water",
        "dessert" : "apple"

]
```

## HOW TO CONNECT TO THE REMOTE API

This will be hosted in aws on the following IP: 34.208.253.148

Note: Communication with the API must be through HTTP no HTTPS
