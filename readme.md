## React Native Caching App with Image Upload and Sync

This document outlines the functionalities and implementation approach for a React Native application that manages image caching, upload, and synchronization.

**Features:**

- Home screen with header displaying "Home" title.
- Upload button to select and upload images from mobile storage.
- Sync button to synchronize images with a server.
- Image list showcasing cached images with information about their sync status.
- Unique filename generation for uploaded images using a reliable library.
- Image upload functionality using appropriate tools to send POST requests to the server.
- Image synchronization with the server using established methods for data retrieval.
- Downloading of server images not present in the cache.
- Error handling for storage access, network requests, and upload/sync processes.

**API Endpoints:**

- Base URL: [https://caching-app-ashen.vercel.app](https://caching-app-ashen.vercel.app)
- GET /images: Returns a list of uploaded images, including deleted image markers.
- POST /images/upload: Uploads an image using form data with the key "image".

**Implementation Approach:**

1. **Screens:**

   - `HomeScreen`: Displays image list, upload button, and sync button.

2. **HomeScreen Components:**

   - Header: Renders title and buttons.
   - ImageList: Displays cards with cached images and sync status.

3. **Upload Functionality:**

   - Accesses multiple images from storage using appropriate libraries.
   - Generates unique filenames for each image.
   - Checks if the image is already uploaded by comparing filenames with downloaded images.
   - Uploads un-uploaded images using established methods for sending data to the server.
   - Tracks upload success/failure and updates cache information accordingly.

4. **Sync Functionality:**

   - Fetches image list from the server using established methods for data retrieval.
   - Identifies and deletes deleted images from the cache based on server response.
   - Downloads missing images from the server and stores them in the cache.
   - Updates the image list to reflect changes after sync.

5. **Initial Image Download:**

   - Downloads images not present in the cache during `componentDidMount` of `HomeScreen`.
   - Stores downloaded images in the cache with their filenames.

6. **Error Handling:**

   - Implements error handling for storage access, network requests, and upload/sync processes.
   - Displays user-friendly error messages.

7. **Caching:**
   - Uses reliable libraries for storing and retrieving images from the cache.
   - Consider using a more advanced caching library for additional functionalities.
