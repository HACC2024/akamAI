# Summary of the App

This app is a Hawaii-focused chatbot and activity explorer. It provides users with information about Hawaii, including local activities and events, using Vertex AI for generating content and Google APIs for additional data. The app consists of two main functionalities:

1. **Chat Interface**: Users can interact with a chatbot to ask questions about Hawaii. The chatbot uses Vertex AI to generate responses based on user queries.
2. **Explore Page**: Displays a grid of activities related to Hawaii. Users can click on activities to view more details, including travel time and sustainability information.

# Overview of Individual Code Files

1. **main.dart**
   - **Purpose**: Initializes the Firebase app and sets up the main entry point of the application.
   - **Key Functions**:
     - Initializes Firebase using the provided configuration.
     - Launches the MyApp widget, which sets up the main navigation structure.

2. **tab_navigation.dart**
   - **Purpose**: Manages the navigation between the chat screen and the explore page using a PageView.
   - **Key Functions**:
     - Initializes the activityModel for Vertex AI.
     - Fetches initial activities for the explore page.
     - Provides a horizontally swipeable interface between the chat and explore pages.

3. **chat_screen.dart**
   - **Purpose**: Manages the chat interface where users interact with the chatbot.
   - **Key Functions**:
     - Initializes Vertex AI models for chat and activity suggestions.
     - Handles sending messages and receiving responses from the chatbot.
     - Fetches and displays activity suggestions based on user queries.
     - Uses utility functions to fetch weather data, images, and travel times.

4. **explore_page.dart**
   - **Purpose**: Displays a grid of activities that users can explore.
   - **Key Functions**:
     - Uses a GridView to display activities fetched from Vertex AI.
     - Handles user interactions with activities, opening detailed views when clicked.

5. **activity_card.dart**
   - **Purpose**: Defines the UI and behavior of individual activity cards.
   - **Key Functions**:
     - Displays activity details such as title, description, and image.
     - Handles click events to show a full-page view with additional information like travel time and sustainability.

6. **activity_utils.dart**
   - **Purpose**: Contains utility functions related to activities.
   - **Key Functions**:
     - `fetchActivitySuggestions`: Calls Vertex AI to generate a list of activities based on user queries, location, and weather conditions.
     - Uses a controlled JSON schema to ensure structured responses from Vertex AI.

7. **api_utils.dart**
   - **Purpose**: Contains utility functions for external API calls.
   - **Key Functions**:
     - `fetchWeatherData`: Retrieves weather forecasts from the National Weather Service API.
     - `fetchImageFromPexels`: Fetches images from the Pexels API based on a search query.
     - `fetchTravelTime`: Uses the Google Maps API to calculate travel time between two locations.

8. **location_utils.dart**
   - **Purpose**: Manages location services.
   - **Key Functions**:
     - `determinePosition`: Requests and retrieves the user's current location using the Geolocator package.

# External Calls

-  **Vertex AI**: Used for generating chat responses and activity suggestions. The app initializes a chat session and requests content using a controlled JSON schema.
-  **Weather API**: Fetches weather data from the National Weather Service to provide context for activity suggestions.
-  **Pexels API**: Retrieves images related to activities to enhance the visual experience in the app.
-  **Google Maps API**: Calculates travel times to activity locations, considering live traffic conditions.

# Additional Notes
- **API Keys**: Some API keys are 'exposed' in the deployed app. However, they are public-facing and don't pose a significant risk even if someone gains access to them; this applies to Pexels, Weather.gov, and Firebase sync keys.
-  **Permissions**: The app requests location, camera, microphone, and photo permissions to provide a full-featured user experience. May not work correctly on web version.


# akamAI Chat & Explore App Demo
- **Link**: https://drive.google.com/file/d/1dSGzSYofdswmdkbPBftIF5UJSix-wNJk
