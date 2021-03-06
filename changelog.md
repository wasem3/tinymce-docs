---
layout: default
title: Changelog
description: The history of TinyMCE releases.
keywords: changelog
class: changelog
---

> This is the {{site.productname}} Community version changelog. For information about the latest {{site.cloudname}} or {{site.enterpriseversion}} Release, see: [{{site.productname}} Release Notes]({{site.baseurl}}/release-notes/).

{% capture changelog %}

## Version 5.2.1 March 25, 2020
* Fixed the "is decorative" checkbox in the image dialog clearing after certain dialog events.
* Fixed possible uncaught exception when a `style` attribute is removed using a content filter on `setContent`.
* Fixed the table selection not functioning correctly in Microsoft Edge 44 or higher.
* Fixed the table resize handles not functioning correctly in Microsoft Edge 44 or higher.
* Fixed the floating toolbar drawer disconnecting from the toolbar when adding content in inline mode.
* Fixed `readonly` mode not returning the appropriate boolean value.
* Fixed the `forced_root_block_attrs` setting not applying attributes to new blocks consistently.
* Fixed the editor incorrectly stealing focus during initialization in Microsoft Internet Explorer.
* Fixed dialogs stealing focus when opening an alert or confirm dialog using an `onAction` callback.
* Fixed inline dialogs incorrectly closing when clicking on an opened alert or confirm dialog.
* Fixed the context toolbar overlapping the menu bar and toolbar.
* Fixed notification and inline dialog positioning issues when using `toolbar_location: 'bottom'`.
* Fixed the `colorinput` popup appearing offscreen on mobile devices.
* Fixed special characters not being found when searching by "whole words only".
* Fixed an issue where dragging images could cause them to be duplicated.
* Fixed context toolbars activating without the editor having focus.
* Fixed an issue where removing the background color of text did not always work.
* Fixed an issue where new rows and columns in a table did not retain the style of the previous row or column.

## Version 5.2.0 February 13, 2020
* Added the ability to apply formats to spaces.
* Added new `toolbar_location` setting to allow for positioning the menu and toolbar at the bottom of the editor.
* Added new `toolbar_groups` setting to allow a custom floating toolbar group to be added to the toolbar when using `floating` toolbar mode.
* Added new `link_default_protocol` setting to `link` and `autolink` plugin to allow a protocol to be used by default.
* Added new `placeholder` setting to allow a placeholder to be shown when the editor is empty.
* Added new `tinymce.dom.TextSeeker` API to allow searching text across different DOM nodes.
* Added a drop shadow below the toolbar while in sticky mode and introduced Oxide variables to customize it when creating a custom skin.
* Added `quickbars_image_toolbar` setting to allow for the image quickbar to be turned off.
* Added iframe and img `loading` attribute to the default schema. Patch contributed by ataylor32.
* Added new `getNodeFilters`/`getAttributeFilters` functions to the `editor.serializer` instance.
* Added new `a11y_advanced_options` setting to allow additional accessibility options to be added.
* Added new accessibility options and behaviours to the image dialog using `a11y_advanced_options`.
* Added the ability to use the window `PrismJS` instance for the `codesample` plugin instead of the bundled version to allow for styling custom languages.
* Added error message events that fire when a resource loading error occurs.
* Changed the default schema to disallow `onchange` for select elements.
* Changed the fallback `toolbar_mode` value from false to `wrap`. The value false has been deprecated.
* Changed `toolbar_drawer` setting to `toolbar_mode`. `toolbar_drawer` has been deprecated.
* Changed iframe mode to set selection on content init if selection doesn't exist.
* Changed table related icons to align them with the visual style of the other icons.
* Changed and improved the visual appearance of the color input field.
* Changed fake caret container to use `forced_root_block` when possible.
* Changed the `requireLangPack` API to wait until the plugin has been loaded before loading the language pack.
* Changed the formatter so `style_formats` are registered before the initial content is loaded into the editor.
* Changed media plugin to use https protocol for media urls by default.
* Changed the parser to treat CDATA nodes as bogus HTML comments to match the HTML parsing spec. A new `preserve_cdata` setting has been added to preserve CDATA nodes if required.
* Fixed incorrect parsing of malformed/bogus HTML comments.
* Fixed `quickbars` selection toolbar appearing on non-editable elements.
* Fixed bug with alignment toolbar buttons sometimes not changing state correctly.
* Fixed the `codesample` toolbar button not toggling when selecting code samples other than HTML.
* Fixed content incorrectly scrolling to the top or bottom when pressing enter if when the content was already in view.
* Fixed `scrollIntoView` potentially hiding elements behind the toolbar.
* Fixed editor not respecting the `resize_img_proportional` setting due to legacy code.
* Fixed flickering floating toolbar drawer in inline mode.
* Fixed an issue where the template plugin dialog would be indefinitely blocked on a failed template load.
* Fixed the `mscontrolselect` event not being unbound on IE/Edge.
* Fixed Confirm dialog footer buttons so only the "Yes" button is highlighted.
* Fixed `file_picker_callback` functionality for Image, Link and Media plugins.
* Fixed issue where floating toolbar drawer sometimes would break if the editor is resized while the drawer is open.
* Fixed incorrect `external_plugins` loading error message.
* Fixed resize handler was not hidden for ARIA purposes. Patch contributed by Parent5446.
* Fixed an issue where content could be lost if a misspelled word was selected and spellchecking was disabled.
* Fixed validation errors in the CSS where certain properties had the wrong default value.
* Fixed an issue where forced root block attributes were not applied when removing a list.
* Fixed an issue where the element path isn't being cleared when there are no parents.
* Fixed an issue where width and height in svg icons containing `rect` elements were overridden by the CSS reset.
* Fixed an issue where uploading images with `images_reuse_filename` enabled and that included a query parameter would generate an invalid URL.
* Fixed the `closeButton` property not working when opening notifications.
* Fixed keyboard flicker when opening a context menu on mobile.
* Fixed issue where plus icon svg contained strokes.

## Version 5.1.6 January 28, 2020
* Fixed `readonly` mode not blocking all clicked links.
* Fixed legacy font sizes being calculated inconsistently for the `FontSize` query command value.
* Fixed changing a tables row from `Header` to `Body` incorrectly moving the row to the bottom of the table.
* Fixed the context menu not showing in certain cases with hybrid devices.
* Fixed the context menu opening in the wrong location when the target is the editor body.
* Fixed the `image` plugin not respecting the `automatic_uploads` setting when uploading local images.
* Fixed security issue related to parsing HTML comments and CDATA.

## Version 5.1.5 December 19, 2019
* Fixed the UI not working with hybrid devices that accept both touch and mouse events.
* Fixed a bug with pasting image URLs when _paste as text_ is enabled.
* Fixed the `charmap` dialog initially focusing the first tab of the dialog instead of the search input field.
* Fixed an exception being raised when inserting content if the caret was directly before or after a `contenteditable="false"` element.

## Version 5.1.4 December 11, 2019
* Fixed dialog contents disappearing when clicking a checkbox for right-to-left languages.
* Fixed the `legacyoutput` plugin registering legacy formats after editor initialization, causing legacy content to be stripped on the initial load.
* Fixed search and replace not cycling through results when searching using special characters.
* Fixed the `visualchars` plugin converting HTML-like text to DOM elements in certain cases.
* Fixed an issue with the `paste` plugin not sanitizing content in some cases.
* Fixed HTML comments incorrectly being parsed in certain cases.

## Version 5.1.3 December 4, 2019
* Fixed sticky toolbar not undocking when fullscreen mode is activated.
* Fixed the "Current Window" target not applying when updating links using the link dialog.
* Fixed disabled menu items not highlighting when focused.
* Fixed touch events passing through dialog collection items to the content underneath on Android devices.
* Fixed keyboard navigation of the Help dialog's Keyboard Navigation tab.
* Fixed search and replace dialog disappearing when finding offscreen matches on iOS devices.
* Fixed performance issues where sticky toolbar was jumping while scrolling on slower browsers.

## Version 5.1.2 November 19, 2019
* Fixed desktop touch devices using `mobile` configuration overrides.
* Fixed unable to disable the new scrolling toolbar feature.
* Fixed touch events passing through any pop-up items to the content underneath on Android devices.
* Fixed the table selector handles throwing JavaScript exceptions for non-table selections.
* Fixed `cut` operations not removing selected content on Android devices when the `paste` plugin is enabled.
* Fixed inline toolbar not constrained to the window width by default.
* Fixed context toolbar split button chevrons pointing right when they should be pointing down.
* Fixed unable to access the dialog footer in tabbed dialogs on small screens.
* Fixed mobile table selectors were hard to select with touch by increasing the size.
* Fixed mobile table selectors moving when moving outside the editor.
* Fixed inline toolbars collapsing when using sliding toolbars.
* Fixed block textpatterns not treating NBSPs as spaces.
* Fixed backspace not merging blocks when the last element in the preceding block was a `contenteditable="false"` element.
* Fixed toolbar buttons that only contain text labels overlapping on mobile devices.
* Fixed `quickbars` quickimage picker not working on mobile.
* Fixed fullscreen not resizing in an iOS **WKWebView** component.

## Version 5.1.1 October 28, 2019
* Fixed font formats containing spaces being wrapped in `&quot;` entities instead of single quotes.
* Fixed alert and confirm dialogs losing focus when clicked.
* Fixed clicking outside a modal dialog focusing on the document body.
* Fixed the context toolbar not hiding when scrolled out of view.

## Version 5.1.0 October 17, 2019
* Added touch selector handles for table selections on touch devices.
* Added border width field to Table Cell dialog.
* Added touch event listener to media plugin to make embeds playable.
* Added oxide styling options to notifications and tweaked the default variables.
* Added additional padding to split button chevrons on touch devices, to make them easier to interact with.
* Added new platform detection functions to `Env` and deprecated older detection properties.
* Added `inputMode` config field to specify inputmode attribute of `input` dialog components.
* Added new `inputMode` property to relevant plugins/dialogs.
* Added new `toolbar_sticky` setting to allow the iframe menubar/toolbar to stick to the top of the window when scrolling.
* Changed default setting for `toolbar_drawer` to `floating`.
* Changed mobile phones to use the `silver` theme by default.
* Changed some editor settings to default to `false` on touch devices:

    - `menubar`(phones only).
    - `table_grid`.
    - `resize`.
    - `object_resizing`.
* Changed toolbars and context toolbars to sidescroll on mobile.
* Changed context menus to render as horizontal menus on touch devices.
* Changed the editor to use the `VisualViewport` API of the browser where possible.
* Changed visualblocks toolbar button icon and renamed `paragraph` icon to `visualchars`.
* Changed Oxide default for `@toolbar-button-chevron-color` to follow toolbar button icon color.
* Changed the `urlinput` dialog component to use the `url` type attribute.
* Fixed Safari desktop visual viewport fires resize on fullscreen breaking the restore function.
* Fixed scroll issues on mobile devices.
* Fixed context toolbar unable to refresh position on iOS12.
* Fixed ctrl+left click not opening links on readonly mode and the preview dialog.
* Fixed Slider UI component not firing `onChange` event on touch devices.
* Fixed notifications overlapping instead of stacking.
* Fixed inline dialogs positioning incorrectly when the page is scrolled.
* Fixed inline dialogs and menus not repositioning when resizing.
* Fixed inline toolbar incorrectly stretching to the full width when a width value was provided.
* Fixed menu chevrons color to follow the menu text color.
* Fixed table menu selection grid from staying black when using dark skins, now follows border color.
* Fixed Oxide using the wrong text color variable for menubar button focused state.
* Fixed the autoresize plugin not keeping the selection in view when resizing.
* Fixed textpattern plugin throwing exceptions when using `forced_root_block: false`.
* Fixed missing CSS fill styles for toolbar button icon active state.
* Fixed an issue where the editor selection could end up inside a short ended element (such as `br`).
* Fixed browser selection being lost in inline mode when opening split dropdowns.
* Fixed backspace throwing an exception when using `forced_root_block: false`.
* Fixed floating toolbar drawer expanding outside the bounds of the editor.
* Fixed the autocompleter not activating immediately after a `br` or `contenteditable=false` element.
* Fixed an issue where the autocompleter would incorrectly close on IE 11 in certain edge cases.

## Version 5.0.16 September 24, 2019
* Added new `referrer_policy` setting to add the `referrerpolicy` attribute when loading scripts or stylesheets.
* Added a slight background color to dialog tab links when focused to aid keyboard navigation.
* Fixed media poster value not updating on change.
* Fixed `openlink` was not registered as a toolbar button.
* Fixed failing to initialize if a script tag was used inside a SVG.
* Fixed double top border showing on toolbar without menubar when `toolbar_drawer` is enabled.
* Fixed unable to drag inline dialogs to the bottom of the screen when scrolled.
* Fixed notifications appearing on top of the toolbar when scrolled in inline mode.
* Fixed notifications displaying incorrectly on IE 11.

## Version 5.0.15 September 2, 2019
* Added a dark `content_css` skin to go with the dark UI skin.
* Changed the enabled state on toolbar buttons so they don't get the hover effect.
* Fixed missing CSS active state on toolbar buttons.
* Fixed `onChange` callback not firing for the colorinput dialog component.
* Fixed context toolbars not showing in fullscreen mode.

## Version 5.0.14 August 19, 2019
* Added an API to reload the autocompleter menu with additional fetch metadata.
* Fixed missing toolbar button border styling options.
* Fixed image upload progress notification closing before the upload is complete.
* Fixed inline dialogs not closing on escape when no dialog component is in focus.
* Fixed plugins not being filtered when defaulting to mobile on phones.
* Fixed toolbar more drawer showing the content behind it when transitioning between opened and closed states.
* Fixed focus not returning to the dialog after pressing the "Replace all" button in the search and replace dialog.
* Removed Oxide variable `@menubar-select-disabled-border-color` and replaced it with `@menubar-select-disabled-border`.

## Version 5.0.13 August 6, 2019
* Changed modal dialogs to prevent dragging by default and added new `draggable_modal` setting to restore dragging.
* Changed the nonbreaking plugin to insert nbsp characters wrapped in spans to aid in filtering. This can be disabled using the `nonbreaking_wrap` setting.
* Changed backspace behaviour in lists to outdent nested list items when the cursor is at the start of the list item.
* Fixed sidebar growing beyond editor bounds in IE 11.
* Fixed issue with being unable to keyboard navigate disabled toolbar buttons.
* Fixed issues with backspace and delete in nested contenteditable true and false elements.
* Fixed issue with losing keyboard navigation in dialogs due to disabled buttons.
* Fixed _MouseEvent.mozPressure is deprecated_ warning in Firefox.
* Fixed `default_link_target` not being respected when `target_list` is disabled.
* Fixed mobile plugin filter to only apply to the mobile theme, rather than all mobile platforms.
* Fixed focus switching to another editor during mode changes.
* Fixed an exception being thrown when clicking on an uninitialized inline editor.
* Fixed unable to keyboard navigate to dialog menu buttons.
* Fixed dialogs being able to be dragged outside the window viewport.
* Fixed inline dialogs appearing above modal dialogs.

## Version 5.0.12 July 18, 2019
* Added ability to utilize UI dialog panels inside other panels.
* Added help dialog tab explaining keyboard navigation of the editor.
* Changed the "Find and Replace" design to an inline dialog.
* Fixed issue where autolink spacebar event was not being fired on Edge.
* Fixed table selection missing the background color.
* Fixed removing shortcuts not working for function keys.
* Fixed non-descriptive UI component type names.
* Fixed UI registry components rendering as the wrong type when manually specifying a different type.
* Fixed an issue where dialog checkbox, input, selectbox, textarea and urlinput components couldn't be disabled.
* Fixed the context toolbar not using viable screen space in inline/distraction free mode.
* Fixed the context toolbar overlapping the toolbar in various conditions.
* Fixed IE11 edge case where items were being inserted into the wrong location.

## Version 5.0.11 July 4, 2019
* Fixed packaging errors caused by a rollup treeshaking [bug](https://github.com/rollup/rollup/issues/2970).
* Fixed the customeditor component not able to get data from the dialog api.
* Fixed collection component tooltips not being translated.

## Version 5.0.10 July 2, 2019
* Added support for all HTML color formats in `color_map` setting.
* Changed backspace key handling to outdent content in appropriate circumstances.
* Changed default palette for forecolor and backcolor to include some lighter colors suitable for highlights.
* Changed the search and replace plugin to cycle through results.
* Fixed inconsistent types causing some properties to be unable to be used in dialog components.
* Fixed an issue in the Oxide skin where dialog content like outlines and shadows were clipped because of overflow hidden.
* Fixed the search and replace plugin not resetting state when changing the search query.
* Fixed backspace in lists not creating an undo level.
* Fixed the editor to cancel loading in quirks mode where the UI is not supported.
* Fixed applying fonts not working when the name contained spaces and numbers.
* Fixed so that initial content is retained when initializing on list items.
* Fixed inefficient font name and font size current value lookup during rendering.
* Fixed mobile font copied into the wrong folder for the oxide-dark skin.
* Fixed an issue where resizing the width of tables would produce inaccurate results.
* Fixed a memory leak in the Silver theme.
* Fixed alert and confirm dialogs using incorrect markup causing inconsistent padding.
* Fixed an issue in the Table plugin with `table_responsive_width` not enforcing units when resizing.
* Fixed leading, trailing and sequential spaces being lost when pasting plain text.
* Fixed exception being thrown when creating relative URIs.
* Fixed focus is no longer set to the editor content during mode changes unless the editor already had focus.

## Version 5.0.9 June 26, 2019
* Fixed print plugin not working in Firefox.

## Version 5.0.8 June 18, 2019
* Added back support for multiple toolbars.
* Added support for .m4a files to the media plugin.
* Added new `base_url` and `suffix` editor init options.
* Fixed incorrect padding for select boxes with visible values.
* Fixed selection incorrectly changing when programmatically setting selection on contenteditable false elements.
* Fixed sidebar background being transparent.
* Fixed the build to remove duplicate iife wrappers.
* Fixed bogus autocompleter span appearing in content when the autocompleter menu is shown.
* Fixed toolbar font size select not working with legacyoutput plugin.
* Fixed the legacyoutput plugin incorrectly aligning images.
* Fixed remove color not working when using the legacyoutput plugin.
* Fixed the font size menu applying incorrect sizes when using the legacyoutput plugin.
* Fixed scrollIntoView not working when the parent window was out of view.
* Fixed the print plugin printing from the wrong window in IE11.
* Fixed content CSS loaded over CORS not loading in the preview plugin with content_css_cors enabled.
* Fixed the link plugin missing the default "None" option for link list.
* Fixed small dot visible with menubar and toolbar disabled in inline mode.
* Fixed space key properly inserts a nbsp before/after block elements.
* Fixed native context menu not showing with images in IE11.
* Fixed inconsistent browser context menu image selection.

## Version 5.0.7 June 5, 2019
* Added new toolbar button and menu item for inserting tables via dialog.
* Added new API for adding/removing/changing tabs in the Help dialog.
* Added highlighting of matched text in autocompleter items.
* Added the ability for autocompleters to work with matches that include spaces.
* Added new `imagetools_fetch_image` callback to allow custom implementations for cors loading of images.
* Added `'http'` and `https` options to `link_assume_external_targets` to prepend `http://` or `https://` prefixes when URL does not contain a protocol prefix. Patch contributed by francoisfreitag.
* Changed annotations navigation to work the same as inline boundaries.
* Changed tabpanel API by adding a `name` field and changing relevant methods to use it.
* Fixed text color not updating all color buttons when choosing a color.
* Fixed the autocompleter not working with fragmented text.
* Fixed the autosave plugin no longer overwrites window.onbeforeunload.
* Fixed infinite loop in the paste plugin when IE11 takes a long time to process paste events. Patch contributed by lRawd.
* Fixed image handle locations when using `fixed_toolbar_container`. Patch contributed by t00.
* Fixed the autoresize plugin not firing `ResizeEditor` events.
* Fixed editor in fullscreen mode not extending to the bottom of the screen.
* Fixed list removal when pressing backspace after the start of the list item.
* Fixed autocomplete not triggering from compositionend events.
* Fixed `file_picker_callback` could not set the caption field on the insert image dialog.
* Fixed the autocompleter menu showing up after a selection had been made.
* Fixed an exception being thrown when a file or number input has focus during initialization. Patch contributed by t00.

## Version 5.0.6 May 22, 2019
* Added `icons_url` editor settings to enable icon packs to be loaded from a custom url.
* Added `image_uploadtab` editor setting to control the visibility of the upload tab in the image dialog.
* Added new api endpoints to the wordcount plugin and improved character count logic.
* Changed plugin, language and icon loading errors to log in the console instead of a notification.
* Fixed the textpattern plugin not working with fragmented text.
* Fixed various toolbar drawer accessibility issues and added an animation.
* Fixed issues with selection and ui components when toggling readonly mode.
* Fixed so readonly mode works with inline editors.
* Fixed docked inline toolbar positioning when scrolled.
* Fixed initial value not being set on bespoke select in quickbars and toolbar drawer.
* Fixed so that nbsp entities aren't trimmed in white-space: pre-line elements.
* Fixed `mceInsertLink` command inserting spaces instead of url encoded characters.
* Fixed text content floating on top of dialogs in IE11.

## Version 5.0.5 May 9, 2019
* Added menu items to match the **forecolor/backcolor** toolbar buttons.
* Added default directionality based on the configured language.
* Added styles, icons, and tests for RTL mode.
* Fixed autoresize not working with floating elements or when media elements finished loading.
* Fixed incorrect vertical caret positioning in IE 11.
* Fixed submenu anchoring hiding overflowed content.
* Removed unused and hidden validation icons to avoid displaying phantom tooltips.

## Version 5.0.4 April 23, 2019
* Added back URL dialog functionality, which is now available via `editor.windowManager.openUrl()`.
* Added the missing throbber functionality when calling `editor.setProgressState(true)`.
* Added function to reset the editor content and `undo`/`dirty` state via `editor.resetContent()`.
* Added the ability to set menu buttons as `active`.
* Added `editor.mode` API, featuring a custom editor mode API.
* Added better styling to `floating` toolbar drawer.
* Added the new premium plugins to the Help dialog plugins tab.
* Added the linkchecker context menu items to the default configuration.
* Fixed image context menu items showing on placeholder images.
* Fixed dialog labels and text color contrast within notifications/alert banners to satisfy WCAG 4.5:1 contrast ratio for accessibility.
* Fixed the `selectbox` and `colorpicker` items not being translated.
* Fixed toolbar drawer `sliding` mode to correctly focus the editor when tabbing via keyboard navigation.
* Fixed positioning of the styleselect menu in iOS while using the mobile theme.
* Fixed the `menubutton` `onSetup` callback to be correctly executed when rendering the menu buttons.
* Fixed `default_link_target` setting to be correctly utilized when creating a link.
* Fixed `colorpicker` floating marginally outside its container.
* Fixed `disabled` menu items displaying as `active` when hovered.
* Removed redundant mobile wrapper.

## Version 5.0.3 March 19, 2019
* Changed empty nested-menu items within the style formats menu to be disabled or hidden if the value of `style_formats_autohide` is `true`.
* Changed the entire phrase 'Powered by Tiny' in the status bar to be a link instead of just the word 'Tiny'.
* Changed `formatselect`, `styleselect`, and `align` menus to use the `mceToggleFormat` command internally.
* Fixed toolbar keyboard navigation to work as expected when `toolbar_drawer` is configured.
* Fixed text direction buttons to display the correct pressed state in selections that have no explicit `dir` property.
* Fixed the mobile editor to clean up properly when removed.
* Fixed quickbar toolbars to add an empty box to the screen when it is set to `false`.
* Fixed an issue where pressing the **Delete/Backspace** key at the edge of tables was creating incorrect selections.
* Fixed an issue where dialog collection items (emoticon and special character dialogs) couldn't be selected with touch devices.
* Fixed a type error introduced in TinyMCE version 5.0.2 when calling `editor.getContent()` with nested bookmarks.
* Fixed an issue that prevented default icons from being overridden.
* Fixed an issue where **Home/End** keys wouldn't move the caret correctly before or after `contenteditable=false` inline elements.
* Fixed styles to be preserved in IE 11 when editing via the `fullpage` plugin.
* Fixed the `link` plugin context toolbar missing the open link button.
* Fixed inconsistent dialog component spacing.

## Version 5.0.2 March 5, 2019
* Added presentation and document presets to `htmlpanel` dialog component.
* Added missing `fixed_toolbar_container` setting that has been reimplemented in the Silver theme.
* Added a new toolbar setting `toolbar_drawer` that moves toolbar groups which overflow the editor width into either a *sliding* or *floating* toolbar section.
* Changed the build process to include package lock files in the dev distribution archive.
* Fixed inline dialogs that did not have aria attributes.
* Fixed the UI registry to include default icons to enhance flexibility and allow use outside of toolbar buttons.
* Fixed a memory leak related to select toolbar items.
* Fixed a memory leak due to format changed listeners that were never unbound.
* Fixed an issue where content may have been lost when using permanent bookmarks.
* Fixed the `quicklink` toolbar button not rendering in the `quickbars` plugin.
* Fixed an issue where menus were generating invalid HTML in some cases.
* Fixed an issue that could cause the mobile theme to show a blank white screen when the editor was inside an `overflow:hidden` element.
* Fixed mobile theme using a transparent background and not taking up the full width on iOS.
* Fixed the template plugin dialog missing the `description` field.
* Fixed input dialog components using an invalid default `type` attribute.
* Fixed an issue where pressing the Backspace/Delete keys before or after page break elements wouldn't move the caret.
* Fixed an issue in the table plugin where menu items and toolbar buttons weren't showing correctly based on the selection.
* Fixed inconsistent button focus styles in Firefox.
* Fixed the resize icon floating left when all status bar elements were disabled.
* Fixed the resize handle to not show in fullscreen mode.

## Version 5.0.1 February 21, 2019
* Added H1-H6 toggle button registration to the silver theme.
* Added code sample toolbar button will now toggle on when the cursor is in a code section.
* Added new settings to the emoticons plugin to allow additional emoticons to be added.
* Fixed an issue where adding links to images would replace the image with text.
* Fixed an issue where the inline editor could use fractional pixels for positioning.
* Fixed an issue where uploading non-image files in the Image Plugin upload tab threw an error.
* Fixed an issue in the media plugin that was causing the source URL and height/width to be lost in certain circumstances.
* Fixed an issue with the Context Toolbar not being removed when clicking outside of the editor.
* Fixed an issue where clicking 'Remove link' wouldn't remove the link in certain circumstances.
* Fixed an issue where the media plugin would fail when parsing dialog data.
* Fixed an issue where retrieving the selected content as text didn't create new lines.
* Fixed incorrect keyboard shortcuts in the Help dialog for Windows.
* Fixed an issue where JSON serialization could produce invalid JSON.
* Fixed production CSS including references to source maps.
* Fixed development CSS was not included in the development zip.
* Fixed the `autocompleter` matches predicate not matching on the start of words by default.
* Fixed an issue where the page could be scrolled with modal dialogs open.
* Fixed an issue where autocomplete menus would show an icon margin when no items had icons.
* Fixed an issue in the `quickbars` plugin where images incorrectly showed the text selection toolbar.
* Fixed an issue that caused the inline editor to fail to render when the target element already had focus.
* Removed paste as text notification banner and `paste_plaintext_inform` setting.

## Version 5.0.0 February 4, 2019
* Added links and registered names with `*` to denote premium plugins in Plugins tab of Help dialog.
* Changed TinyMCE 5 mobile skin to look more uniform with the desktop.
* Fixed an issue where tab panel heights weren't sizing properly on smaller screens and weren't updating on resize.
* Fixed an issue where tab panel heights weren't sizing properly on smaller screens and weren't updating on resize.
* Fixed image tools not having any padding between the label and slider.
* Fixed Blacklisted table,` th` and `td` as inline editor target.
* Fixed context toolbar toggle buttons not showing the correct state.
* Fixed missing separators in the spellchecker context menu between the suggestions and actions.
* Fixed notification icon positioning in alert banners.
* Fixed a typo in the word count plugin name.
* Fixed `charmap` and emoticons dialogs not having a primary button.
* Fixed an issue where resizing wouldn't work correctly depending on the box-sizing model.

## Version 5.0.0-rc-2 January 22, 2019
* Added screen reader accessibility for sidebar and status bar.
* Changed Emoticons and Charmap dialogs to be screen reader accessible.
* Changed the `textpattern` plugin to support nested patterns properly and to allow running a command with a value for a pattern with a start and an end.
* Changed checkboxes to use a boolean for its state, instead of a string.
* Changed formatting menus, so they are registered and made the align toolbar button use an icon instead of text.
* Fixed the link dialog such that it will now retain class attributes when updating links.
* Fixed "Find and replace" not showing in the "Edit" menu by default.
* Fixed dropdown buttons missing the 'type' attribute, which could cause forms to be incorrectly submitted.
* Fixed `emoticon` and `charmap` search not returning expected results in certain cases.
* Fixed blank rel_list values throwing an exception in the link plugin.
* Removed unnecessary 'flex' and unused 'colspan' properties from the new dialog APIs.

## Version 5.0.0-rc-1 January 8, 2019
* Added editor settings functionality to specify title attributes for toolbar groups.
* Added icons instead of button text to improve Search and Replace dialog footer appearance.
* Added `tox-dialog__table` instead of `mce-table-striped` class to enhance Help dialog appearance.
* Added title attribute to iframes so, screen readers can announce iframe labels.
* Added a wordcount menu item, that defaults to appearing in the tools menu.
* Changed the `autocompleter` to only show when it has matched items.
* Changed **SizeInput** labels to **Height** and **Width** instead of **Dimensions**.
* Changed the build process to minify and generate ASCII only output for the emoticons database.
* Changed the font select dropdown logic to try to detect the system font stack and show "System Font" as the font name.
* Fixed read-only mode not fully disabling editing content.
* Fixed accessibility issues with the font select, font size, style select, and format select toolbar dropdowns.
* Fixed accessibility issues with split dropdowns.
* Fixed the `legacyoutput` plugin to be compatible with TinyMCE 5.0.
* Fixed icons not showing correctly in the `autocompleter` popup.
* Fixed an issue where preview wouldn't show anything in Edge under certain circumstances.
* Fixed the height being incorrectly calculated for the `autoresize` plugin.

## Version 5.0.0-beta-1 November 30, 2018
* Added a new `addNestedMenuItem()` UI registry function and changed all nested menu items to use the new registry functions.
* Added `title` attribute to color swatch colors.
* Added `anchorbar` component to anchor inline toolbar dialogs to instead of the toolbar.
* Added support for **toolbar<n>** and **toolbar array** config options to be squashed into a single toolbar and not create multiple toolbars.
* Added error handling for when `forced_root_block` config option is set to `true`.
* Added functionality for the `removed_menuitems` config option.
* Added the ability to use a string to reference menu items in menu buttons and submenu items.
* Changed the name of the "inlite" plugin to "quickbars".
* Changed the background color icon to highlight background icon.
* Changed Help dialog to be accessible to screen readers.
* Changed the color swatch to save selected custom colors to local storage for use across sessions.
* Changed `WindowManager` API - methods `getParams`, `setParams` and `getWindows`, and the legacy `windows` property, have been removed. `alert` and `confirm` dialogs are no longer tracked in the window list.
* Fixed an inline mode issue where the save plugin upon saving can cause content loss.
* Fixed an issue in IE 11 where calling `selection.getContent()` would return an empty string when the editor didn't have focus.
* Removed compat3x plugin.


## Version 5.0.0-preview-4 November 12, 2018
* Added width and height placeholder text to image and media dialog dimensions input.
* Added the ability to keyboard navigate through menus, toolbars, sidebar and the status bar sequentially.
* Added translation capability back to the editor's UI.
* Added `label` component type for dialogs to group components under a label.
* Changed the editor resize handle so that it should be disabled when the `autoresize` plugin is turned on.
* Changed UI text for microcopy improvements.
* Fixed distraction free plugin.
* Fixed contents of the input field selected on focus instead of just receiving an outline highlight.
* Fixed styling issues with dialogs and menus in IE 11.
* Fixed custom style format control not honoring custom formats.
* Fixed context menu not appearing when clicking an image with a caption.
* Fixed directionality of UI when using an RTL language.
* Fixed page responsiveness with multiple inline editors.
* Fixed empty toolbar groups appearing through an invalid configuration of the `toolbar` property.
* Fixed text not being retained when updating links through the link dialog.
* Fixed edit image context menu, context toolbar, and toolbar items being incorrectly enabled when selecting invalid images.
* Fixed emoji type ahead being shown when typing URLs.
* Fixed toolbar configuration properties incorrectly expecting string arrays instead of strings.
* Fixed the block formatting toolbar item not showing a "Formatting" title when there is no selection.
* Fixed clicking disabled toolbar buttons hiding the toolbar in inline mode.
* Fixed `EditorResize` event not being fired upon editor resize.
* Fixed tables losing styles when updating through the dialog.
* Fixed context toolbar positioning to be more consistent near the edges of the editor.
* Fixed table of contents plugin now works with v5 toolbar APIs correctly.
* Fixed the `link_context_toolbar` configuration not disabling the context toolbar.
* Fixed the link context toolbar showing incorrect relative links.
* Fixed the alignment of the icon in alert banner dialog components.
* Fixed the visual blocks and visual char menu options not displaying their toggled state.
* Fixed the editor not displaying as fullscreen when toggled.
* Removed the tox-custom-editor class that was added to the wrapping element of codemirror.

## Version 5.0.0-preview-3 October 18, 2018
* Changed editor layout to use modern CSS properties over manually calculating dimensions.
* Changed `autoresize_min_height` and `autoresize_max_height` configurations to `min_height` and `max_height`.
* Changed `Whole word` label in Search and Replace dialog to `Find whole words only`.
* Fixed bugs with editor width jumping when resizing and the iframe not resizing to smaller than `150px` in height.
* Fixed mobile theme bug that prevented the editor from loading.
* Fixed long toolbar groups extending outside of the editor instead of wrapping.
* Fixed dialog titles so they are now the proper case.
* Fixed color picker default to be `#000000` instead of `#ff00ff`.
* Fixed "match case" option on the **Find and Replace** dialog is no longer selected by default.
* Fixed vertical alignment of toolbar icons.
* Fixed toolbar icons not appearing on IE11.

## Version 5.0.0-preview-2 October 10, 2018
* Added swatch is now shown for `colorinput` fields, instead of the `colorpicker` directly.
* Added `fontformats` and `fontsizes` menu items.
* Changed configuration of color options has been simplified to `color_map`, `color_cols`, and `custom_colors`.
* Changed `height` configuration to apply to the editor frame (including menubar, toolbar, status bar) instead of the content area.
* Fixed `styleselect` not updating the displayed item as the cursor moved.
* Fixed preview iframe not expanding to the dialog size.
* Fixed 'meta' shortcuts not translated into platform-specific text.
* Fixed tabbed dialogs (Charmap and Emoticons) shrinking when no search results returned.
* Fixed a bug where alert banner icons were not retrieved from icon pack.
* Fixed component styles to flex, so they fill large dialogs.
* Fixed editor flashing unstyled during load (still in progress).
* Removed `colorpicker` plugin, it is now in the theme.
* Removed `textcolor` plugin, it is now in the theme.

## Version 5.0.0-preview-1 October 1, 2018
* Developer preview 1

{% endcapture %}

{{ changelog | pretty_changelog }}
