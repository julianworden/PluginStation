# PluginStation
A repository for hosting the public releases for Plugin Station, an audio plugin management app.

## Release Notes
Here are the release notes for all public and beta versions of Plugin Station.

### v1.0.4
- Fix bug where user may be stuck at app startup if an error is thrown after detecting changes to installed plugins
- Add verbiage to Installed Plugin rescan screen to make it clearer that the preparation for rescan may take a couple minutes
- Fix bug where enabling the Manufacturer filter for plugins but not actually selecting a manufacturer would cause a "Failed to perform search, received unexpected response with code: 400. Please try again." error message.

### v1.0.3
- Fix a bug causing some users to see a "Trouble reaching the Branch servers. Please try again shortly" error message when attempting to purchase a subscription.

### v1.0.2
- Fix a bug causing some users to experience crashes during plugin scanning
- Fix a bug causing some users to be unable to purchase a subscription during onboarding
- Improve messaging after plugin scan to better explain that plugins are regularly added to the Plugin Station database in order from most frequently installed to least frequently installed, and that notification emails are sent out to all users whenever an update relevant to them occurs

### v1.0.1
- Fix a bug where Plugin Station would occasionally crash on startup
- Fix a bug where a plugin's details screen was showing an incorrect value for whether or not that plugin is available as a perpetual license
- Update third party SDKs to prevent future bugs

### v1.0.0
- The first ever public, non-beta version of Plugin Station
- Fix a bug where plugin versions may unexpectedly appear to have a "." at the end under some circumstances
- The app icon now shows a badge indicating the user's number of unread notifications, if they've provided permission to show the badge
- Fix various bugs for admins

### v0.1.0-beta.2
- Fix bugs with installed DAW scanning and presentation. **In order for these to changes to take effect, the user must rescan their installed DAWs in Settings > Installed Software > Rescan Installed DAWs**
    - Fix a bug where, for users with certain installed DAWs, Plugin Station would indicate that other versions of those DAWs are installed, even though they aren't
    - Fix an issue in the Installed DAWs tab where users with many installed DAWs will not see all of there installed DAWs
- Users will now receive an email, a macOS system notification, and a notification in the Notifications tab of Plugin Station when new plugins that they have installed are added to the Plugin Station database. These notifications serve to inform the user that they can now perform more operations with these plugins, and they are sent in batches by the Plugin Station admin that's performing the plugin creation. Clicking one of these system notifications will open Plugin Station and take the user to a screen with more details about it.

### v0.1.0-beta.1
- Thank you so much for being one of the first people to ever try Plugin Station, other than myself. After almost a year and a half of working on this app, it's surreal to finally get it out into the world. I'm so excited to hear your feedback. - Julian
