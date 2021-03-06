# Actions on Google: Facts about Google Sample using Node.js and Cloud Functions for Firebase

This is a knowledgable Assistant app that shares interesting facts about Google.
The sample introduces advanced features like custom entities, contexts,
and deep links. Use this app and you might see that it even knows about a
subject other than Google!

## Setup Instructions

See the developer guide and release notes at [https://developers.google.com/actions/](https://developers.google.com/actions/) for more details.

### Steps
1. Use the [Actions on Google Console](https://console.actions.google.com) to add a new project with a name of your choosing.
1. Click *Use API.AI* and then *Create Actions on API.AI* to open the API.AI console.
1. Click *Save* to save the project.
1. Click on the gear icon to see the project settings.
1. Select *Export and Import*.
1. Select *Restore from zip*. Follow the directions to restore from the `FactsAboutGoogle.zip` file in this repo.
1. Deploy the fulfillment webhook provided in the `functions` folder using [Google Cloud Functions for Firebase]
(https://firebase.google.com/docs/functions/):
  1. Create a Firebase project in the [Firebase Console](https://console.firebase.google.com) if you don't have one already.
  1. Follow the instructions to [set up and initialize Firebase SDK for Cloud Functions](https://firebase.google.com/docs/functions/get-started#set_up_and_initialize_functions_sdk). Make sure to reply "N" when asked to overwrite existing files by the Firebase CLI.
  1.Run `firebase deploy --only functions` and take note of the endpoint where the fulfillment webhook has been published. It should look like `Function URL (factsAboutGoogle): https://us-central1-YOUR_PROJECT.cloudfunctions.net/factsAboutGoogle`
1. Go back to the API.AI console and select *Fulfillment* from the left navigation menu. Enable *Webhook*, set the value of *URL* to the `Function URL` from the preiovus step, then click *Save*.
1. Select *Intents* from the left navigation menu. Select the `quit_facts` intent, scroll down to the end of the page and click *Action on Google*, check "End Conversation" and then click *Save*.
1. Select *Integrations* from the left navigation menu and open the *Settings* menu for Actions on Google.
1. Enter the following intents as "Additional triggering intents"
    * `choose_fact`
    * `choose_cats`
1. Click *Test*.
1. Click *View* to open the Actions on Google simulator.
1. Type `Talk to my test app` in the simulator, or say `OK Google, talk to my test app` to any Actions on Google enabled device signed into your developer account.

For more detailed information on deployment, see the [documentation](https://developers.google.com/actions/samples/).

## References and How to report bugs
* Actions on Google documentation: [https://developers.google.com/actions/](https://developers.google.com/actions/).
* If you find any issues, please open a bug here on GitHub.
* Questions are answered on [StackOverflow](https://stackoverflow.com/questions/tagged/actions-on-google).

## How to make contributions?
Please read and follow the steps in the [CONTRIBUTING.md](CONTRIBUTING.md).

## License
See [LICENSE.md](LICENSE.md).

## Terms
Your use of this sample is subject to, and by using or downloading the sample files you agree to comply with, the [Google APIs Terms of Service](https://developers.google.com/terms/).

## Google+
Actions on Google Developers Community on Google+ [https://g.co/actionsdev](https://g.co/actionsdev).
