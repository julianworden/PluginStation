# PluginStation
A repository for hosting the public releases for Plugin Station, an audio plugin management app.

## Release Notes
Here are the release notes for all public and beta versions of Plugin Station.

### v1.0.13
- Fix bug where some plugins were appearing multiple times in the installed plugins list
- Fix bug where some DAWs were unexpectedly going undetected during DAW scanning
- Fix bug where DAW version numbers were not being formatted correctly

### v1.0.12
- NEW FEATURE: Due to popular demand, you can now "Ignore" plugins in System Warnings! Simply click the Ignore button next to a plugin in a System Warning to ignore it, or use the checkboxes to select and ignore multiple plugins at a time. NOTE: Only recognized plugins with known manufacturer information can be ignored, and ignoring a plugin will stop it from triggering any and all system warnings
- Add a "Release Notes" button to the Plugin Station tab in the macOS Menu Bar. Click this button to open your browser and view a page where you can see the release notes for every version of Plugin Station

### v1.0.11
- Fix a bug where a "Trouble reaching the Branch servers, please try again shortly." error message was occasionally being shown to some users when clicking a plugin in the Browse Plugins list

### v1.0.10
- The user is now prompted to indicate how they heard about Plugin Station during onboarding
- The user is now prompted to provide a cancellation reason when they are cancelling their subscription

### v1.0.9
- Fix a bug where a superseded plugin system warning would show up for plugins that have the superseded and superseding plugin installed. No longer will a warning be shown for a superseded plugin if the latest plugin that supersedes it is installed
- Fix a bug where the app does not properly handle plugins that have the same name as another plugin in the database. This is now handled properly both during plugin scanning, and when changes happen during and not during app operation
- Fix 2 bugs in the screen that shows when plugin changes are made when the app is or is not running. The first was showing irrelevant installed version change data when a single format for a plugin was uninstalled/installed. The second was affecting what would happen if 2 plugins with the same name were changed at the same time. Only one of the 2 plugins was showing up, now both are

### v1.0.8
- Implement CMD + ',' keyboard shortcut to open app preferences to follow standard macOS conventions. Also add a 'Preferences' button to the Plugin Station tab in the macOS menu bar for the same reason
- Further improve stability when a plugin is uninstalled both when the app is and is not running

### v1.0.7
- Fix a bug where uninstalling a plugin while the app is or is not running may cause a crash under some conditions
- Fix a bug where the app was not properly handling when an email address with both uppercase and lowercase letters was entered during account creation

### v1.0.6
- Fix bug where some users experience an infinite loading screen after making changes to installed plugins and reopening the app

### v1.0.5
- Implement perpetual licenses. Perpetual licenses can now be purchased, upgraded, and used in Plugin Station
- Fix bug where AAX plugins were not being scanned properly
- Fix a bug where the user was not being properly redirected into the app after purchasing a new subscription or switching subscription plans

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
