## Topics – The "What":
The product will be a web application that uses an image detection model to identify foods from photos, and then associates them with known allergens. The user will be able to ask the model a question, "Did you have any symptoms after eating this?" and the model will provide a response based on the user's previous input of symptoms. This will help users track their reactions to certain foods and identify potential allergies.

## Design Considerations:

1. **Image Detection Accuracy:** Make sure that the model itself is very good at recognizing different a few common allergens. Training data will be obtained online from popular food image datasets.
2. **Ingredient Database:** A very list common ingredients in common foods.
3. **User Interface:** User-friendly for taking photos and answering questions by Streamlit.
4. **Symptom Tracking:** Track if the food, and thus its ingredients, resulted in a reaction. This will be inaccurate to start due to many foods share ingredients, but will slowly become more accurate with more data.
5. **Minimal Viable Product:** To start, only a test user account will be available and its data will be stored in Azure in json format.

## Solution Overview:

1. **Food Identification:** Implement or integrate an image recognition model with PyTorch (probably) to identify foods from their images.
2. **Ingredient Mapping:** Map the identified foods to common ingredients through a database.
3. **User Interactions:** Employ Streamlit to interact with the user and ask whether they experienced any symptoms after the consumption of the identified food.
4. **Data Logging:** Log user responses in a JSON file kept on a cloud service. This will be used to track positive and negative reactions to ingredients.
5. **Alert System:** The user can also take pictures of food to know if it's safe to eat. In the event that a food taken in by picture has a high reaction rate (>~10%), previous data will alert the user to it.
6. **Dashboard:** Show the user a dashboard where they can see ingredients they are possibly allergic too.
7. **Future features:** Help the user meal plan, shop, and pick food from a menu they can eat based on their data. Providing a search feature could also be useful to lookup foods they can't take a picture of. Also, provide a feature for user's to specify their known allergies, and weight certain possible allergens more heavily. For example, if they are diagnosed to be allergic to ingredient a, statistically they are also more likely to be allergic to ingredient b, so if their reaction rate to ingredient b is over half the normal minimum threshold, alert them. Maybe even past data could be edited to help narrow down allergies using medical diagnosis. For example, if they thing they have a milk allergy, but it turns out they don't, then force milk to a 0% rate, but if gluten is often present in foods with milk, weight it more heavily as a possible trigger.

## Topics – The "Why":
1. **Health and Safety:** Assists users in avoiding foods that may provoke allergic reactions.
2. **Ease of Use:** Through an entire food-related symptom and potential allergen tracking process, it eases things because the user won't have to focus on logging every ingredient and can instead enjoy their meal and get insights overtime.
3. **Data-Driven Insights:** Enhances its recommendations with time by making them more accurate and useful based on the data.

## Implementation Considerations:

1. **Model Training:** Scouting a wide-ranging dataset to train the image detection model in PyTorch.
2. **Database Creation:** That the database of food ingredients should be complete and up to date.
3. **User Feedback:** This would just be a simple interface, developed in Streamlit, which would be used to gather quick and easy feedback from a user about their symptoms.
4. **Initial Privacy and Security:** There is no need for this to form part of the prototype, as there is only data from one test user.
5. **Cloud Integration:** This will integrate via Azure for hosting models and storing data.
6. **Health and safety disclaimers:** A user should always see a disclaimer on the screen that this is not a medical tool, and should only be used to assist in collecting data for actual doctors to use as a starting point for clinical allergy testing.
7. **When is there enough data:** Because many entires will need to have been logged for proper predations