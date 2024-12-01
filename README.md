# Creative Writing Prompt Generator

This web application allows users to generate random writing prompts, submit their stories, and upvote others' stories. It utilizes Firebase for authentication (via email/password or anonymous login), storing prompts, stories, and user upvotes in Firestore.

## Features

- **Random Writing Prompts**: Generate a random writing prompt from a predefined set.
- **Submit Stories**: Write and submit your own stories based on the prompts.
- **Upvote Stories**: Upvote other users' stories. Each user can upvote a story only once.
- **User Authentication**: Users can log in anonymously or sign up with an email/password to manage their stories and upvotes.
- **Story Display**: View recently submitted stories along with the upvote count.

## Technologies Used

- **Frontend**: HTML, CSS, JavaScript (ES Modules)
- **Backend**: Firebase (Firestore for database, Firebase Authentication for user management)
- **Deployment**: Firebase Hosting (optional)

## Requirements

To run this project locally, you need the following:

- A modern web browser (e.g., Chrome, Firefox)
- A Firebase account (you’ll need to set up your Firebase project)

## Setting Up the Project

### 1. Firebase Setup

1. **Create a Firebase Project**:
   - Go to the [Firebase Console](https://console.firebase.google.com/).
   - Click on "Add project" and follow the steps to create a new Firebase project.

2. **Enable Firebase Authentication**:
   - In the Firebase Console, navigate to the **Authentication** section.
   - Enable **Email/Password** and/or **Anonymous Authentication** depending on your needs.

3. **Enable Firestore**:
   - Go to the **Firestore Database** section in the Firebase Console.
   - Create a Firestore database (use **Start in test mode** for development).

4. **Get Firebase Configuration**:
   - In the **Project Settings** of your Firebase project, go to the **General** tab.
   - Copy the Firebase config object (you’ll use it in the code).

5. **Create Firestore Collections**:
   - **prompts**: This collection will store predefined writing prompts.
   - **stories**: This collection will store stories submitted by users.
   - Each document in the **stories** collection will contain:
     - `text`: The story text.
     - `upvotes`: The number of upvotes the story has.
     - `userId`: The ID of the user who submitted the story.
     - `timestamp`: When the story was submitted.
   - **upvotes** (subcollection under stories): Stores individual upvotes for each story.
     - `userId`: The user ID of the person who upvoted the story.

### 2. Clone or Download the Repository

Clone the project or download the files directly from the repository:

```bash
git clone https://github.com/your-username/creative-writing-prompt-generator.git
```
3. **Set Up Firebase Configuration**:
In the `index.html` file, replace the placeholder `firebaseConfig` object with your actual Firebase project credentials:

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID",
  measurementId: "YOUR_MEASUREMENT_ID"
};
```
4. Serve the Application Locally
You can simply open the `index.html` file in your browser. Alternatively, you can use a local server (like Live Server for Visual Studio Code or http-server) to serve the files locally.

6. **How to Use the Application**:
 - **Sign Up**:
      Sign up with your email and password or log in using the provided login form.
      After logging in, you can submit stories and upvote others' stories.
 - Generate a Prompt:
      Click the "Get a Random Writing Prompt" button to generate a random writing prompt.
 - Submit a Story:
      Write your story in the provided text area.
      Click "Submit Your Story" to save it to the Firestore database.
 - Upvote Stories:
      Click the "Upvote" button on any story to upvote it. You can only upvote a story once.
      The upvote count will update when you successfully upvote a story.
Logout when you're done.
7. **Contributing**:
Feel free to fork this repository and create a pull request if you have any improvements or bug fixes. Contributions are always welcome!
