# PluginStation
A repository for hosting the public releases for Plugin Station, the audio industry's most powerful audio plugin management app.

## Release Notes
Here are the release notes for all public and beta versions of Plugin Station.

### 1.5.0
- **NEW FEATURE: Custom Plugin Tags**
  - The user can now create custom tags to organize their installed plugins any way they like
  - To create a tag, click the new "Tags" tab in the left sidebar of the app and then select the "+" button in toolbar at the top. To add plugins to that tag, you can click the "Tag Plugins +" button that appears after selecting a tag from the tags list. The user can also right click plugins in the list shown in the Installed Plugins tab > Add Tag, or click the "+ Add Tag" button that appears after selecting a plugin from the installed plugins list
  - The previously mentioned "Tags" tab in the left sidebar reveals all of the tags the user has created. Selecting a tag from the tags list shows more details about that tag, along with each plugin the tag is applied to. By default, tagged plugins will only show here if they are installed on the System Profile that the user is currently using. To view all of the installed plugins that are tagged with the selected tag, the user can disable the "Only show plugins installed on this System Profile" toggle
  - To edit or delete a tag, the user can right click it from the tags list and click delete or edit, or select the tag from the tags list and use the edit and delete buttons in the toolbar at the top
  - To remove a tag from a plugin, the user can right click it from the Installed Plugins list in the Installed Plugins tab > Remove Tags. An installed plugin details screen also lists an x mark next to each tag, the user can click it to remove that tag from that plugin
  - The user can filter their installed plugins based on one or more tags using a new Tags filter in the installed plugin filter menu
  - Plugins that have one or more tags now show a tag icon everywhere plugins are listed — the Installed Plugins list, Storage Manager, the Uninstall Assistant, and every System Warning details screen (Out-of-Date, Superseded, Unsupported macOS Version, Duplicate Installed Plugin Files, and Unneeded Installed Plugin Format). Hovering over the icon shows that plugin's tag(s)
  - An installed plugin's details screen now shows that plugin's tags in the About section
- **Miscellaneous Improvements**
  - Make it easier to access resources regarding how to use Plugin Station
    - Settings now includes a Resources tab in the left sidebar. This tab includes links to various video tutorials about Plugin Station, along with a link to the FAQ page on the Plugin Station website 
    - The Help tab in the macOS Menu Bar now includes buttons to quickly navigate to all of the previously mentioned resources that are also accessible via Settings > Resources. Previously, this Help tab existed but it didn't do anything
  - Redesign the System Profile State details screen so that it's more consistent with the design of the other lists throughout the app
  - It is now possible to filter based on multiple types and manufacturer names at one time via the filter menus in the Installed Plugins and Browse Plugins tabs
  - Add a macOS 27 (Golden Gate) callout to the filter menus in the Installed Plugins and Browse Plugins tab regarding why it is not yet possible to filter based on macOS 27 support
- **Bug Fixes**
  - Fix a bug where the Duplicate Installed Plugin Files System Warning was detecting non-duplicate plugins as duplicates
  - Fix a bug where uninstalling an archived plugin would fail under some conditions 
  - Fix a bug where it was possible for the red out-of-sync plugins banner to appear following an uninstall/archive. This should never happen, as the app syncs the change with the user's account in the background

### 1.4.1
- **Miscellaneous Improvements**
  - Choosing a folder as a custom plugin location will now present a confirmation/warning alert if the selected folder contains no VST, VST3, AU, AAX, or Waves plugin files
  - Add more base-level system folders that the user cannot select as custom plugin folder locations, such as Music, Documents, Desktop, Downloads, or Library. These folders tend to contain a significant amount of data that Plugin Station cannot index efficiently, leading the app to operate extremely slowly when one of them is selected
  - Add more descriptive error messages to alerts that appear when a plugin archiving error occurs
  - It is now significantly easier to uninstall/archive plugins in bulk via the Duplicate Installed Plugin System Warning. Now, the user can use the checkbox in the top left corner of the list to select specific duplicate files based on file path and archive status. For example, if the user has a series of duplicate files in one specific folder, like /Desktop/Plugins, the app will allow them to select all duplicate files in /Desktop/Plugins in one click so that they can uninstall or archive them all without selecting them individually
  - Plugin rescanning speeds have been significantly improved. In the vast majority of cases, a plugin rescan will now complete in as little as half the time that it did before  
- **Bug Fixes**
  - Fix a rare bug where, under some circumstances, Plugin Station would detect non-plugin files as plugin files. This was mainly affecting users using custom plugin folder locations that did not contain any plugin files
    - The first time an existing user launches 1.4.1, Plugin Station performs a one-time cleanup of their account. It checks every installed plugin on the user's account for file paths that do not point at real plugin files, removes those paths from both the local cache and the user's account, and deletes the entry entirely when nothing valid remains. This cleanup never deletes a file from the user's computer — it only corrects the app's records. New users skip this entirely, as plugin scans/rescans are now set up to never run into this issue in the first place
  - Fix various Archive-related bugs that would surface upon archiving/unarchiving plugins that have duplicate files installed
  - Fix a bug where some System Warning details views were not immediately refreshing after archiving files from elsewhere in the app
  - Fix a bug where archiving every plugin in an Unneeded Installed Plugin Format System Warning left its details screen open on an empty list instead of dismissing it
  - Fix a bug where users with no DAWs installed were not shown any Unneeded Installed Plugin Format System Warnings, even though every installed plugin format is unneeded in that situation
  - Fix various bugs that made it possible for the user's installed plugins to drift out of sync with what was on their account. Plugin Station now performs various operations behind the scenes to ensure that this drift doesn't happen, but if it ever does, there are also other mechanisms in place to automatically bring the system back into sync with the user's account
  - Fix a bug where, under some conditions, the red out-of-sync plugins banner would appear even when nothing had actually changed on the user's system
  - Fix a bug where applying plugin filters with every option turned off behaved differently from clicking the Clear button
  - Fix a bug where a plugin installed in two locations could report a different version from one launch to the next. Plugin Station now always describes the newer of the two builds, so a current plugin is no longer reported as out of date because an older copy was found first
  - Fix a bug where, on small screens, the Installed Manufacturer Details view only showed one plugin at a time in the list of installed plugins from the selected manufacturer

### 1.4.0
- **NEW FEATURE: Plugin Archiving**
    - By very popular demand, users can now "Archive" plugins using Plugin Station. Archiving is meant to serve as a middle ground between leaving plugin files in your DAW's "view" (a place it can see them), and uninstalling them completely. This is useful for a variety of use cases:
        - **Troubleshooting:** When a plugin file is causing a crash in a DAW, it can be difficult to tell which plugin is causing the crash, especially in sessions with many plugins. Archiving gives the user an easy way to move plugins in and out of folders that the DAW sees to determine what's causing the issue
        - **Cancelled Plugin Subscriptions/Free Trials:** Upon cancelling a plugin subscription or after cancelling a free trial, the user may not want to completely uninstall the plugin(s). However, every time they open their DAW, many manufacturers show popup windows telling the user they have plugins installed that they don't have a license for. To avoid this, the user can simply archive all of the plugins they no longer have a license for, and then unarchive them once they need to start using them again
        - **Using Multiple DAWs:** Some users have workflows that require multiple DAWs, and they have plugins that they prefer to only use in one and not the other. Plugin Station makes it easy to archive plugins you don't need in whatever DAW you're using as you go back and forth, resulting in a much more streamlined plugin list in the DAW
    - To use archiving:
        - Existing users must navigate to Settings > Installed Software > Rescan Installed Plugins > Select Archive Folder. Choose a folder to use as the Archive folder, this is where all archived plugin files will go when you archive them. Choose an "Organize By:" option to choose how to organize the files within subfolders in the Archive folder. The option doesn't change anything within the app, it's just meant to make the folder easier to look at in Finder. Complete a Rescan
        - Brand new users will see the Select Archive Folder button during onboarding
    - Many existing screens now allow the user to archive plugins:
        - Installed Plugins list
            - Select multiple plugins by clicking on plugins while holding the CMD key on the keyboard, or by clicking a plugin > holding Shift > and clicking the bottom most plugin in a range of plugins. Right click one and use one of the archiving/unarchiving options
            - Use these selection methods in combination with installed plugin filters to archive plugins in bulk based on specific criteria, like manufacturer name, unsupported macOS versions, and more
        - Installed Plugin Details
        - Installed Manufacturer Details
        - Uninstall Assistant
        - System Warnings tab
        - Storage Manager
        - Almost anywhere that uninstalling was previously possible
    - New filters are now available in the Installed Plugins List's filters to allow for showing only/hiding archived plugins
- **System Warnings Settings**
    - The settings screen presented by clicking the gear icon at the top of the System Warnings tab now presents new settings for hiding archived plugins and always showing warnings about specific installed plugin formats
    - Enable the "Hide Archived Plugins In System Warnings" option to make sure that **fully** archived plugins do not trigger any system warnings
    - Enable the "Always Warn Me About Installed <pluginFormat> Plugins" option to make sure that the app always presents a warning about an installed plugin format, even if a DAW is installed that supports it
- **Miscellaneous Changes**
    - Make it possible to uninstall specific formats in bulk by selecting multiple plugins in the Installed Plugins list and right clicking one of them
    - Upon syncing changes to installed plugins with the user's account, the popup that appears to show the changes now has more readable messages in the "Updated" tab. For example, if a user had a plugin's VST and VST3 files installed and then decided to install the AU file later, the "Updated" tab now says "Installed AU Format" for that plugin to make it easier to tell what changed for that plugin
- **Miscellaneous Bug Fixes**
    - Fix a bug when uninstalling multiple plugins where it was possible for some plugins to uninstall successfully, while others silently failed to uninstall
    - Fix a bug where it was possible to select a plugin in the Installed Plugins list, enable a filter/sort or search, select other plugins, and see a "Multiple Plugins Selected" message
    - Fix a bug where the duplicate installed plugins system warning would not detect duplicate Waves files if they were within the same 'Plug-Ins v<versionNumber>' folder
    - Fix a bug where the app slowed down in the Installed Plugins tab while certain plugins were selected in the list

### 1.3.7
- Add optimizations to the app's license code redemption system
- Make it possible to click the 'Open Message in Default Mail App' button in the 'Contact Us' screen without needing to type a subject and message
- Fix a bug where Blue Cat Audio plugin versions were not being compared properly

### 1.3.6
- **Plugin Station's First Birthday!**
    - Implement a new birthday-themed app icon to celebrate Plugin Station's 1st birthday
    - Add confetti and first birthday-related text to app startup and onboarding screens
- **Plugin Station X Install Assistant Collaboration**
    - Plugin Station has partnered with Install Assistant! Install Assistant is an incredibly useful utility that makes it possible to run your plugin installers in bulk. Simply download your installers and drag them into Install Assistant. Whether you're restoring a computer or just running installers for a few plugins you just bought, it's sure to save you loads of time
    - Plugins that support Install Assistant will now be listed as such within plugin details screens. Clicking the button will open Install Assistant if it’s installed, or take the user to the page on the Install Assistant site where they can get an exclusive coupon if they don’t
    - Plugin filter menus now allow the user to filter plugins based on whether or not they support Install Assistant, making it very easy to see what needs to be installed by the user and what the user can easily install in bulk with Install Assistant
    - Settings now has a new tab called "Partnerships", which includes an Install Assistant section that the user can use to access their exclusive Install Assistant coupon
- **Miscellaneous**
    - Plugin descriptions are now truncated with a 'See More' button
    - In plugin details screens, the manufacturer logo + plugin name column is now always a fixed width and height

### 1.3.5
- **Easier Selection Across All Lists**
    - Lists with selectable items now support click and drag to make selections, so you can select multiple items in one continuous gesture. For example, clicking and holding on one list row and then dragging to the next one will select both rows
    - Lists and tables with selectable rows now change color when the user hovers over them to make it clearer that they are clickable
    - For lists that contain check boxes in their rows: The user can now click anywhere in a row — not just on the checkbox — to select an item, making rows much easier to select
- **Keyboard Shortcut Support**
    - The user can now press the Enter key on their keyboard to trigger the primary action of most screens
    - Lists with selectable rows now support Shift + Click to more closely mimic the behavior of native macOS lists. For example, clicking the top-most row, holding the Shift key, and clicking the bottom-most row will select those 2 rows and every row in between them 
- **Bug Fixes**
    - Fix a bug where, for some plugins, Show In Finder and Uninstall actions would not reveal or remove all of a plugin's files when viewing data fetched via search or filters
    - Fix an Uninstall Assistant bug where, for some plugins, selecting the checkbox for one plugin would select the equivalent checkbox for other plugins
    - Fix a bug in the Installed Plugins list where a loading spinner could appear under the last plugin, even when all of the relevant plugins were already showing

### v1.3.4
- **System Warnings**
  - System Warning detail screens now show a progress bar while their data is loading
  - Fix a bug where not all System Warning detail screens were sorting their data in alphabetical order
  - Fix a bug where ignoring the last plugin in a System Warning was not dismissing the corresponding details view
  - Fix a related bug where transferring the last of your license keys off a deleted activation location was not immediately clearing the Plugin License Keys On Deleted Activation Location System Warning
  - Fix a bug where some System Warning details views were not updating immediately after a plugin was ignored or un-ignored. Instead, they were forcing all System Warnings to reload
- **Uninstall Assistant**
  - Update the loading progress bar such that it uses the same style as the ones in System Warnings
  - Fix a bug where the Select All/Deselect All checkbox was not limited to the searched plugins when a search was active
- **Installed Manufacturers**
  - The installed plugins list inside an Installed Manufacturer's details screen now vertically expands to fill all available space, so more plugins are visible at once without scrolling
- **App Launch**
  - Fix a bug where the splash screen was no longer animating away when the app finished launching

### v1.3.3
- **Out-of-Date Installed Plugins System Warning**
    - Add an "Ignore (This Update)" button to the Out-of-Date Installed Plugins System Warning screen. The user can now use the "..." button next to any plugin to ignore that specific update, and only see future updates following the one that they ignored. This option is also now available in the "Ignore Selected" menu at the top right corner of the list
    - Display notes about various manufacturers so that the user has more context about certain quirks that certain manufacturers have in how they distribute updates to users
    - Add a button to the top of the window to present text describing what to do in the event that the user is unable to find an update that Plugin Station says is the latest version of a plugin 
    - Fix a bug where, if some plugin formats were out of date while others weren't, this screen would only show the out of date ones and not the up-to-date ones. This was leading users to think the app wasn't properly detecting their plugins, even though they were just not updating all of the formats they had installed
    - Fix a rare bug where some plugin formats wouldn't be shown as out of date/up to date under some conditions
- **Uninstall Assistant**
    - The user can now search and sort the plugins in Uninstall Assistant by using the new search field and sort buttons in the toolbar
    - The manufacturer and "select/deselect all" checkboxes now present menus if the plugins they pertain to contain more than 1 plugin format. For example, if the user has VST3 and AAX plugin files installed by Waves, they will click the Waves checkbox and see options for select/deselect all VST3/AAX. Same for the "select/deselect all" checkbox
    - Fix a bug where scrolling would sometimes appear laggy, especially for users with a lot of plugins installed
- **Installed Plugins List and Details**
    - The user can now select multiple plugins in the Installed Plugins list and right click any of the selected plugins to uninstall them, view their product pages, or view them in Finder.
        - To select plugins that are next to each other: Click the topmost plugin you want to select, hold the Shift key on your keyboard, and then click the bottommost plugin you want to select
        - To select plugins that are not next to each other: Hold the command key while you click on each plugin you want to select
    - Fix a bug where the user would still see uninstalled plugins in the app after uninstalling them if they had applied filters/sorting first
    - Fix a bug where the Visit Manufacturer Website button in an installed plugin's details screen took the user to the product page instead of the manufacturer's homepage
- **Quality-Of-Life Improvements**
    - Installed Manufacturers, Installed Plugins, Storage Manager, and Uninstall Assistant tabs now start fetching data immediately on app startup, making it much quicker to access them after launching Plugin Station
    - Uninstalling a plugin with Plugin Station now instantly removes that plugin from the Installed Plugins, Installed Manufacturers, Storage Manager, Uninstall Assistant, and System Warnings tabs without refreshing all the data in those tabs
    - Ignoring/Un-Ignoring a plugin in a System Warning now automatically updates all System Warnings without having to reload every single one 
- **Storage Manager**
    - Fix a bug where clicking "See All" to expand the "Storage Usage by Manufacturer" or "Storage Usage by Plugin Format" tables would silently collapse back to the default short view after uninstalling a plugin
- **Plugin Rescanning**
    - It is now clearer that the user must rescan their plugins before Custom Locations and Private Folder changes will take effect
- **About This System Profile**
    - Fix a bug where the About This System Profile screen was truncating some of its text
- **System Warnings**
    - Fix bug where if a user has selected a System Warning and then they clear that System Warning by resolving it, the System Warning's details screen would still show
    - Fix a rare bug where the app might crash upon presenting the System Warnings Settings screen presented by the gear icon above the System Warnings list
    - Fix a bug in System Warnings Settings where checking an individual plugin's box and then deleting that plugin individually (without using "Stop Ignoring Selected") would result in the header checkbox at the top of the list remaining checked as if a plugin is still selected
- **Miscellaneous Changes/Fixes**
    - The background sync progress indicator has been redesigned. Instead of a toolbar icon, which was unreliably presenting the info popup when clicked, it now appears as a floating text box in the bottom-right corner of the app's window

### v1.3.2
- NEW FEATURE: The user can now designate a Private Folder of plugins that Plugin Station will completely ignore. Use this on systems with confidential pre-release/beta plugins or plugin versions that you don't want Plugin Station to know about
    - To set a Private Folder, navigate to the plugin scanning screen during onboarding or via Settings > Installed Software > Rescan Installed Plugins. For the latter instructions, you will need to complete a plugin rescan before the Private Folder change will take effect
    - NOTE: New plugins and plugin versions are still not added to the Plugin Station plugin database unless they are publicly visible on the manufacturer's website. This is simply a privacy feature so that confidential data is never on Plugin Station's servers in the first place
- After uninstalling plugins with Plugin Station, all screens in the app now immediately update to reflect the change. Before, a sync was required in order for plugins to appear uninstalled in the app. In cases where many plugins are uninstalled at one time, changes are now synced with the user's account in the background during normal app usage after the files are removed from the user's computer
    - A circular progress indicator appears in the toolbar while a background sync is in progress. Click it to see more details about what's syncing
    - Attempting to quit Plugin Station while a background sync is still running will cause the quit to be deferred. The app will automatically quit once the sync finishes so that no data is lost
- The Installed Plugins list now shows all installed plugins at once instead of loading them in batches while scrolling
- Add the option to uninstall plugins directly from the screen that appears when selecting a Superseded Plugin System Warning. The user can now view the details of plugins from this screen as well
- Make it possible to delete or mark notifications as read/unread directly from the Notifications list using swipe actions, a right-click context menu, or a new icon in the toolbar
- Progress bars are now displayed in various places throughout the app for long operations that are likely to take more than a couple seconds 
- Uninstall Assistant rows now include icons that show details about each plugin at a glance, and it is now possible to show a plugin's details screen from any Uninstall Assistant row
- The Out-of-Date Plugins System Warning screen now show a single version number to represent all installed formats when the available update is the same across all of them, instead of repeating the same version multiple times. If different formats have different new version numbers, they will still be shown like before
- The "Show in Finder" option in an Installed Plugin's details screen now opens the plugin file immediately in Finder if only one format is installed. If multiple formats are installed, a menu is shown with options for each format and a new "Show All In Finder" option that reveals every installed format at once
- Fix a bug where the app was mistaking the SignalGenerator Waves plugin file for the SignalGenerator Avid plugin file
    - For users experiencing this issue: The app should automatically correct this issue after launching this updated version of Plugin Station for the first time
- Fix a bug on macOS Ventura where the red "Plugins Out of Sync" popup would sometimes not appear in realtime after making changes to installed plugins. Previously, the user sometimes had to put the app in the background and bring it back to the foreground for the popup to show
- Fix a bug where deselecting the "Unknown" manufacturer checkbox in Uninstall Assistant would not actually deselect those plugins
- Fix a bug where the "Select All" checkbox in Uninstall Assistant was misaligned with the checkboxes in the rows below it
- Fix a bug in Uninstall Assistant where the same plugin format could appear multiple times for the Waves manufacturer row
- Fix a bug in the Superseded Plugin System Warning details screen where the "Ignore Selected" button was clickable even when no plugins were selected
- Fix a bug where an Installed Plugin's details screen would sometimes not display correctly when opened in its own window
- Fix a bug where the screen showing System Profile deletion progress would sometimes not get dismissed after the deletion completed
- Fix a bug where, in some cases, certain non-plugin files could be detected as installed plugins
    - For users experiencing this issue: The app should automatically correct this issue after launching this updated version of Plugin Station for the first time
- Fix a bug where the Plugin Station window's size and position were not being saved across app launches
- Fix a bug on macOS Ventura where the installed plugin CSV export popup would repeatedly present itself and dismiss in a loop when the user clicked the button to present it

### v1.3.1
- Add options during onboarding for purchasing Enterprise Subscription Plans for up to 80 System Profiles, the previous limit was 20 simply because these new plans hadn't been added yet
- Add a "Redeem License Code" button during onboarding for users who have purchased a Plugin Station license code. This was done in preparation for making it possible for users to purchase a license outside of the Plugin Station app
- Fix a bug where plugin files with unreadable version information were not being displayed as such in various details screens
- Fix a bug where plugin files with unreadable version information were erroneously appearing in the Out-of-Date Plugins System Warning
- Fix a bug where Plugin Station was not detecting a macOS version change if the user downgraded their macOS version
- Fix a bug where the "Select All" checkbox in the Superseded Plugins System Warning was showing the wrong symbol and was not responding to clicks
- Fix a bug where unneeded installed plugin format warnings were erroneously appearing and telling users that they had 0 KB of the unneeded format installed
- Fix a bug where uninstalling a plugin would silently fail under some conditions

### v1.3.0
- NEW FEATURE: A System Warning now appears when you have plugins installed that do not support the macOS version you're currently using
    - To ensure its accuracy, all macOS compatibility data is manually verified via the plugin manufacturer's website or technical support team before its added to the database
- NEW FEATURES: More Installed Plugins filters have been added:
    - Which macOS version(s) a plugin supports
    - Which macOS version(s) a plugin does NOT support
    - Which formats a plugin has installed
    - Whether or not a plugin has been superseded
    - Whether or not a plugin has been discontinued
    - Whether or not a plugin requires an iLok authorization
    - Whether or not a plugin is free
- NEW FEATURE: An "Ignore (This System Warning)" option is now available for plugins in System Warnings. Before, the user could only ignore all System Warnings for a plugin, meaning that if a plugin was ignored, it would no longer show up under any System Warnings. Now, if there's a single System Warning the user does not want a plugin to show up in, they can ignore that plugin for just that System Warning.
    - This new option appears alongside the "Ignore (All System Warnings)", which has the same effect that the Ignore feature had before
- NEW FEATURE: It is now possible to Ignore System Warnings themselves. For example, if the user never wants the Unneeded AAX Plugin Files System Warning to appear, they can Ignore it by right clicking it in the System Warnings list, swiping left on it in the System Warnings list, or clicking the crossed out bell button in the top right corner of its details screen
- The Browse Plugins list now has an icon next to any plugin that does not support the user's current macOS version
- The Installed Plugins list now has icons next to any plugins that are superseded, discontinued, free, or do not support the user's current macOS version
- During onboarding, the user now has to verify their email address before purchasing a subscription or perpetual license to ensure that it's not possible to make an order with an invalid/incorrect email address by mistake
- Add text to the Create Username screen during onboarding to clarify why a username is necessary (sharing System Profiles and future features)
- Add more descriptive text that appears in the Installed Plugins list when filters return no results
- Add an info popup next to a plugin's supported macOS versions that specifies that Plugin Station only tracks macOS compatibility info for macOS Ventura and later
- Improve System Warnings loading times
- While system warning data is loading, the app now shows a redacted view like it does while Installed Plugin data is loading, for example
- Loaded data is now preserved when the user views a System Warning details screen. For example, if the user clicked the Out-Of-Date Plugins System Warning, clicked on a different System Warning, and then went back to the Out-Of-Date Plugins System Warning, the data would have to load again before the user could view it. Now that is not necessary, and the information will still be there when the user goes back

### v1.2.10
- Add a status message that shows in the System Warnings tab to make it clearer to the user what's happening while System Warnings are loading
- Fix a bug where the buttons at the top of the window for creating/editing a plugin license key were not legible in dark mode for users on some macOS versions. These buttons have been replaced with checkboxes so that they're more legible and consistent with the design of the rest of the app
- Fix a bug where the checkbox to select all plugins in the screen showing unneeded installed plugin files wasn't doing anything
- Fix a bug where Ableton Live and FL Studio users were being told they had certain versions of those DAWs installed that weren't actually installed. This fix makes it so that Ableton Live and FL Studio will not get detected on the user's computer if the name of the DAW's .app file is changed. This change was required in order to fix this bug. For other DAWs, they will still get detected if their .app file name changes

### v1.2.9
- Fix a rare bug where the user may see an erroneous "Trouble reaching the Branch servers, please try again shortly" error message after loading plugin details

### v1.2.8
- NEW FEATURE: A free version of Plugin Station is now available! The user can now use a Skip button during onboarding to use a free version of Plugin Station with a limited feature set, all without entering their payment information
- Improve onboarding such that the user no longer has to scroll at any point through the process
- The logos during onboarding are now clickable and lead to the Plugin Station website
- The app's version and copyright information is now displayed during onboarding
- Fix a bug where some users may experience very long load times when loading the details for a plugin
- Fix a bug on macOS Ventura where Uninstall Assistant rows might move strangely when loaded
- Fix a bug where vague error messages were being shown during login and signup whenever an error occurred
- Fix a bug where the app was sometimes freezing after the user created an account, making an app restart necessary before the user could proceed through onboarding

### v1.2.7
- Fix a bug where, under certain conditions, the app was telling users that they had DAWs installed that they didn't have installed. **If you were having this issue: Please rescan your installed DAWs in Settings > Installed Software > Rescan Installed DAWs in order for this fix to take effect**

### v1.2.6
- If a browsed plugin is installed, it just shows as 'Installed' in its details view instead of a very long title showing you the name of the system profile
- Fix a bug where some DAWs may not be detected on the user's system, even though they're in the Plugin Station DAW database. **If you were having issues with undetected DAWs, you will need to rescan your DAWs via Settings > Installed Software > Rescan Installed DAWs**
- Make the out-of-sync popup alert more obvious by giving it a red background
- Fix a rare issue where some users are experiencing a crash on app startup

### v.1.2.5
- Make it possible to filter the plugin database by plugins that support macOS 26 (Tahoe). macOS Tahoe support information is gradually being added
- Change the appearance of the buttons that appear at the top of the screen for creating/editing a plugin license key to be more consistent with other parts of the app
- Fix a bug where an error message about being unable to check for app updates may appear on startup
- Fix a bug where installed unrecognized plugins were showing erroneous out-of-date warnings in their details view
- Fix a rare bug where the app may crash on startup

### v.1.2.4
- NEW FEATURE: The user can now view all of their installed manufacturers from the Installed Manufacturers tab in the left sidebar. After selecting a manufacturer from this tab, the user can much more easily contact their support, view which of their plugins are installed, uninstall all of their plugins, and more
- A manufacturer's logo can now be clicked in various parts of the app, making it easier to access that manufacturer's information. It's now also possible to click the name of the manufacturer in the About section of a plugin's details screen
- The Uninstall button in an installed plugin's details screen is now always a menu that unfolds to present uninstallation options much more clearly than before
- It is now possible to uninstall all of the plugins by a given manufacturer via Storage Manager. Simply navigate to the Storage Usage by Manufacturer section and uses the ellipsis buttons on the right side of each row in the table
- Improve the appearance and functionality of the search suggestion dropdown menu that appears underneath text fields where the user is searching for a manufacturer or plugin name. The user can now use the up arrow key, down arrow key, and return key on their keyboard to navigate through these dropdown menus
- A symbol is now shown next to a selected plugin's supported macOS versions that indicates whether or not the user's current System Profile's macOS version supports the selected plugin
- Improve the appearance of how the supported macOS versions look in the About section in a selected plugin's details screen. They now show as a range instead of showing each one individually
- Visually separate the Uninstall button in a selected installed plugin's Options section
- When exporting a CSV file for a user's installed plugins, the selected columns are now preserved and automatically selected/deselected every time the user exports a CSV file
- Installed Formats are now sorted in alphabetical order in an exported installed plugins CSV file
- The user can now expand and collapse out-of-date plugin manufacturers in the screen that appears when selecting an out-of-date plugins System Warning, making it much easier to navigate when you have a lot of plugins out of date
- The app's splash screen now shows varying messages depending on what stage of startup the user is on
- After uninstalling plugins via Storage Manager, the Storage Manager screen now refreshes instantly. Before, it was required that the user synced their installed plugin changes before the changes would be reflected in Storage Manager
- Add a note to Storage Manager noting that Waves plugin formats cannot be uninstalled individually, so after uninstalling some formats it may appear that some files in those formats are still installed
- Fix a bug where hovering over the symbol next to an installed plugin's installed version would be difficult. There was only a very small part of the symbol you could hover over to present the intended message. The text that appears in these popovers was updated as well
- Fix a bug where macOS Tahoe was not showing as a supported macOS version for plugins that support macOS Tahoe
- Fix a bug where expanding a group of plugins in Uninstall Assistant would sometimes fail

### v1.2.3
- NEW FEATURE: It is now possible to export a CSV file containing info about your installed plugins! You can either export all of your installed plugins, or you can export a subset of them by applying filters at the top of the Installed Plugins list. To access the window to export a CSV file, navigate to the Installed Plugins section in the left sidebar of the app. Above the list that appears, click the icon that looks like a square containing an upward-pointing arrow
- NEW FEATURE: It is now possible to use the Installed Plugins filters to hide or show only unrecognized installed plugins. To access these filters, navigate to the Installed Plugins section in the left sidebar of the app. Above the list that appears, click the icon next to the previously mentioned one
- NEW FEATURE: It is now possible to uninstall all plugin files of a specific plugin format via Storage Manager. Before, this was only possible in Plugin Station if you saw a System Warning telling you that you had an unnecessary plugin format installed. You can also open all of your VST, VST3, AU, or AAX plugin files in Finder via Storage Manager. To access these options, click any of the "..." buttons in the "Storage Usage by Plugin Format" section of Storage Manager
- Many more UI elements now take advantage of Apple's new Liquid Glass design language. Only users running macOS Tahoe (26 and later) will see this change
- Alter the messaging that appears when Plugin Station starts syncing installed plugin changes. This messaging makes it clearer what's happening during long periods of time where it may appear that the app is frozen, but it's actually not
- When you reach the bottom of a fetched batch of plugins in the Browse Plugins and Installed Plugins lists, a spinner now appears to indicate that another batch of plugins is loading
- Fix a bug where it was possible to create or update an Activation Location with no name
- Fix a bug in the Installed Plugins Filters window where the popup would appear too narrow on some OS versions, causing the "Clear" button to overlap with the title at the top of the popup
- Fix a bug where clearing installed plugin filters may cause the first batch of newly fetched plugins to load, but then get stuck loading the next batch
- Fix a bug in the Browse Plugins and Installed Plugins lists where clicking the search field and then modifying filters would cause the loaded plugins to stay the same and not get filtered
- Fix bug where plugin details screens were showing a blank value for the Supported macOS Versions field if a plugin was superseded or discontinued
- Fix a rare bug where some users were experiencing a crash immediately after launching Plugin Station

### v1.2.2
- Plugin Station Enterprise Subscription Plans are now available!
    - Before, the highest number of System Profiles you could have on a single Plugin Station account was 3. Now, with Plugin Station Enterprise Subscription Plans, you can have as many as you need
    - To purchase or upgrade to a Plugin Station Enterprise Subscription Plan, please contact Support at support@julianmichaeltechnologies.com with information about your business (business name, how many computers you plan to use with Plugin Station, etc.) so that we can assist you
- Fix bug where deleting a System Profile was causing the user to get kicked back to onboarding, only for the app to freeze and require a restart
- Fix a bug where deleting a System Profile was not deleting that System Profile's ignored plugins
- Fix a bug where deleting a System Profile was not deleting its corresponding Activation Location if that Activation Location had no license keys activated to it
- Fix a bug on macOS Ventura where the Settings window was not getting dismissed automatically after deleting the System Profile that was currently in use
- Fix cosmetic issues that would appear in the Compare System Profiles tab if the user had more than 2 System Profiles

### v1.2.1
- Add more icons throughout the app for more consistency with macOS Tahoe's design
- Add mention of License Key Manager to onboarding process
- Fix bug where some users may see a 'Failed to fetch plugin by ID.' error message and/or a crash when scanning plugins or syncing new plugin changes
- Fix a bug where the Total Storage Usage chart in Storage Manager would appear to have way too many tick marks along the X Axis for users with hard drives greater than 1 TB
- Fix a bug where using plugin browsing filters and plugin license key filters at the same time was causing issues
- Fix wording in some Uninstall Assistant screens to make their purposes more clear
- Fix bug in various Uninstall Assistant views where drop shadows were getting clipped off and not showing in their entirety
- Fix bug where the Manufacturer Name text field would go off the top of the screen in the screens for plugin browsing and installed plugin filtering

### v1.2.0
- NEW FEATURE: Plugin Station now features a tab in the left sidebar named License Key Manager, which allows the user to more easily manage the license keys for each of their plugins!
    - License Key Manager encrypts each of your license keys using Apple's Keychain and syncs the encrypted license keys across your devices using iCloud. Your license keys never touch the Plugin Station servers
    - Upon launching Plugin Station 1.2.0 for the first time, an Activation Location will automatically be created that represents each of your System Profiles. In Settings > Activation Locations, you can create additional Activation Locations to represent various types of iLok Activation Locations (iLok Cloud, iLok2 dongles, etc.) to make it easier to keep track of where your License Keys are activated
    - If you delete an Activation Location while license keys are still activated to it, you will see a System Warning telling you that you have license keys activated to a deleted activation location
    - Updating a System Profile's nickname/notes will update the corresponding Activation Location's name/notes, and vice versa
- NEW FEATURE: You can now add notes to each of your System Profiles! You will see a text field to add notes upon creating a System Profile. To add notes to an existing System Profile, navigate to Settings > System Profiles > ... > Edit
- Some parts of Plugin Station now have animations to make screen transitions appear more fluid
- Start caching the image that displays at the top of a plugin's details screen so that it appears more quickly on subsequent reloads
- Most macOS Menu Bar options now show icons alongside their titles. Many menus throughout the app also have icons as well. This was done because many menu options now show icons as of macOS 26.0. These icons will not appear in macOS Ventura (13) through Sequoia (15)
- Fix a bug in Storage Manager where clicking the "See All" button in the Largest Plugins section would cause the app to freeze and require a Force Quit
- Fix a rare bug where it was possible for some users to see an erroneous "Unneeded Installed Plugin Format" System Warning under some conditions

### v1.1.4
- Implement macOS 26 (Tahoe) Support
    - Implement a new app icon that visually changes depending on how the user has set the appearance of their icons. For example, if the user sets their icons to appear in Dark mode, Plugin Station's icon will now have a black background with blue in the outlet holes. While icon appearance does not change between modes for users running macOS Ventura through Sequoia, these users will notice that the tag on the Plugin Station icon's plug now appears blue instead of red
    - Adopt the new Liquid Glass design language introduced by Apple. Users running macOS 26.0 and later will now see these new Liquid Glass design elements in Plugin Station
    - Make various, subtle changes so that some elements of the app are more readable and glanceable on macOS Tahoe
- Implement support for plugins manufacturered by Waves
    - Plugin Station will now detect the .bundle Waves plugin files installed on the user's system in /Applications/Waves. Existing users with Waves plugins already installed should see the app sync these plugins with their account the first time they run Plugin Station 1.1.4
    - Plugin Station can perform the same operations with these plugins as it can with plugins from other manufacturers, the only exception being uninstalling individual plugin formats. It is not possible to, for example, uninstall only the VST3 file for a Waves plugin because Waves does not make their VST3, AU, and AAX plugin files visible for each individual plugin. Instead, they install .bundle files that contain each format, along with WaveShell files that interface with DAWs to load these .bundle files.

### v1.1.3
- Fix a bug where the app was properly detecting installed plugin changes and notifying the user about them, but was not actually making the correct, corresponding change to the user's account for some plugins. If you were experiencing this issue, please check on the plugins in question after installing this update. If you still experience issues, perform an installed plugin rescan in Settings > Installed Software > Rescan Installed Plugins and you should not see this issue again. If you do, please contact support@julianmichaeltechnologies.com
- Fix a bug in the out-of-date plugins system warning. Next to the manufacturer of each out-of-date plugin, the app displays a button indicating the best way to get the latest version of that manufacturer's plugins. In cases where there were multiple options for getting the latest version, the button was performing the right action, but it was not labeled properly. For example, in some cases it would tell the user to open an installation manager when it should've told the user to open the manufacturer's Downloads page
- Add clearer messaging during app startup to explain to the user what's happening in the event of a slower-than-usual startup time

### v1.1.2
- Fix a bug where the app would sometimes tell the user that their plugins are out of sync, even though they aren't. This would usually be triggered by navigating through plugin folders in Finder without actually making any changes to any files
- Fix searching so that it returns a max of 25 results instead of the default 10.
- Fix bug in Storage Manager where "Total Hard Drive" had a chart color assigned to it even though that color would never actually appear in the chart since it was covered by all the other colors
- Make it so that black and white cannot be chart colors in Storage Manager because, depending on the user's color scheme, they will not be visible
- Fix a bug on macOS Ventura where searching for plugins will sometimes flicker the fetched plugins, and then show others as if no search occurred
- Fix a bug on macOS Ventura where opening the Browse Plugins or Installed Plugins List will sometimes cause a loop where batches are repeatedly fetched back to back, as opposed to the intended behavior where more plugins only load if the user scrolls down
- Fix a bug on macOS Ventura where many buttons were not sizing properly and were appearing vertically shorter than intended
- Fix a bug on macOS Ventura where, after rescanning DAWs, the window that appears would truncate most of its content instead of showing the user the DAWs that were found

### v1.1.1
- Fix a bug where the icon was not appearing for the System Profiles tab in App Settings for macOS Ventura and Sonoma
- Fix a bug in Uninstall Assistant on macOS Ventura where the uninstall window would reappear and become undismissable after uninstalling plugins
- Fix a bug where the user would see an error message after launching the app if they did not have one of the default plugin folders on their system

### v1.1.0
- NEW FEATURE: Plugin Station now features a tab in the left sidebar named Uninstall Assistant, which allows the user to uninstall many plugins at a time
- The user is no longer required to open a Finder window to delete plugin files. Instead, Plugin Station handles plugin uninstallation automatically
- The app now shows a message in the bottom left corner when installed plugins are altered, as opposed to instantly updating when a change is detected. The user has to click this message in order to sync the changes
- The user is no longer prompted to use an installation manager for uninstalling if that installation manager is not capable of uninstallation plugins
- Manufacturer logos are now cached so that when they appear shortly after having already appeared, they load instantly
- Show the user which plugin's data is being updated while the app is updating detected plugin changes
- Fix a bug on macOS Ventura where Filter and Sort Options popups repeatedly appear and dismiss after clicking the button to present them
- Fix a bug where uninstalling or installing many plugins at a time while the app is running was causing unexpected behavior

### v1.0.14
- Fix bug where an Out-Of-Date Plugins System Warning would show plugin formats as being out of date even if they weren't, but another one was. For example, if a plugin's VST file was out of date it would show that, but it would also show the VST3, AU, and AAX files as being out of date, even if they weren't
- Clicking an Out-Of-Date Plugin Notification will now open up that notification in the Notifications list within the app
- Fix a bug where an error message regarding an unexpectedly missing "Installed Manufacturer" would appear for some users after making changes to installed plugins during and not during app operation

### v1.0.13
- Fix bug where some plugins were appearing multiple times in the installed plugins list
- Fix bug where some DAWs were unexpectedly going undetected during DAW scanning. NOTE: If you were experiencing this issue, please rescan your DAWs via Settings > Installed Software > Rescan Installed DAWs so that Plugin Station can detect your previously unreecognized DAWs
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
