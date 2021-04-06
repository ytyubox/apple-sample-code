
# UIKit Catalog: Creating and Customizing Views and Controls
https://developer.apple.com/documentation/uikit/views_and_controls/uikit_catalog_creating_and_customizing_views_and_controls

- Every UIView, UIControl, Picker
- Diffable CollectionView Datasource
- foldable list
- Localization with *.strings, InfoPlist.strings
- Dynamic font
- Mutilple Storyboard
- include split view, mac catlist 
    ```swift
    #if !targetEnvironment(macCatalyst)
    #endif
    ```

```text
├── Configuration
│   └── SampleCode.xcconfig
├── LICENSE
├── README.md
├── UIKitCatalog
│   ├── ActivityIndicatorViewController.swift
│   ├── AlertControllerViewController.swift
│   ├── AppDelegate.swift
│   ├── Assets.xcassets
│   ├── Base.lproj
│   │   ├── ActivityIndicatorViewController.storyboard
│   │   ├── AlertControllerViewController.storyboard
│   │   ├── ButtonViewController.storyboard
│   │   ├── ColorPickerViewController.storyboard
│   │   ├── Credits.rtf
│   │   ├── CustomPageControlViewController.storyboard
│   │   ├── CustomSearchBarViewController.storyboard
│   │   ├── CustomToolbarViewController.storyboard
│   │   ├── DatePickerController.storyboard
│   │   ├── DefaultPageControlViewController.storyboard
│   │   ├── DefaultSearchBarViewController.storyboard
│   │   ├── DefaultToolbarViewController.storyboard
│   │   ├── FontPickerViewController.storyboard
│   │   ├── ImagePickerViewController.storyboard
│   │   ├── ImageViewController.storyboard
│   │   ├── InfoPlist.strings
│   │   ├── LaunchScreen.storyboard
│   │   ├── Localizable.strings
│   │   ├── Main.storyboard
│   │   ├── PickerViewController.storyboard
│   │   ├── ProgressViewController.storyboard
│   │   ├── SegmentedControlViewController.storyboard
│   │   ├── SliderViewController.storyboard
│   │   ├── StackViewController.storyboard
│   │   ├── StepperViewController.storyboard
│   │   ├── SwitchViewController.storyboard
│   │   ├── TextFieldViewController.storyboard
│   │   ├── TextViewController.storyboard
│   │   ├── TintedToolbarViewController.storyboard
│   │   ├── WebViewController.storyboard
│   │   └── content.html
│   ├── ButtonViewController.swift
│   ├── ColorPickerViewController.swift
│   ├── CustomPageControlViewController.swift
│   ├── CustomSearchBarViewController.swift
│   ├── CustomToolbarViewController.swift
│   ├── DatePickerController.swift
│   ├── DefaultPageControlViewController.swift
│   ├── DefaultSearchBarViewController.swift
│   ├── DefaultToolbarViewController.swift
│   ├── FontPickerViewController.swift
│   ├── ImagePickerViewController.swift
│   ├── ImageViewController.swift
│   ├── OutlineViewController.swift
│   ├── PickerViewController.swift
│   ├── ProgressViewController.swift
│   ├── SceneDelegate.swift
│   ├── SegmentedControlViewController.swift
│   ├── SliderViewController.swift
│   ├── StackViewController.swift
│   ├── StepperViewController.swift
│   ├── SwitchViewController.swift
│   ├── TextFieldViewController.swift
│   ├── TextViewController.swift
│   ├── TintedToolbarViewController.swift
│   ├── UIKitCatalog-Info.plist
│   ├── UIKitCatalog.entitlements
│   └── WebViewController.swift
└── UIKitCatalog.xcodeproj
```


---

# UIKit Catalog: Creating and Customizing Views and Controls


Customize your app’s user interface with views and controls.

[Download](https://docs-assets.developer.apple.com/published/5c11834d2b/UIKitCatalogCreatingAndCustomizingViewsAndControls.zip) 

Availability

*   iOS 14.0+ 
*   Xcode 12.2+
*   Mac Catalyst 14.0+

Framework 

* UIKit


## Overview

This sample guides you through several types of customizations you can make in your iOS app. The sample uses a split-view controller architecture for navigating UIKit views and controls. The primary view controller (`MasterViewController`) shows the available views and controls. When you select one, `Master
View
Controller` shows the secondary view controller associated with it.

The name of each secondary view controller reflects its _target item_. For example, the `Alert
Controller
View
Controller` class shows how to use a `UIAlert
Controller` object. The only exceptions to this rule are `UISearch
Bar` and `UIToolbar`; the sample demonstrates these APIs in multiple view controllers to explain how their controls function and how to customize them. To demonstrate how to manage the complexity of your storyboards, the app hosts all view controllers in a separate storyboard and loaded when needed.

This sample demonstrates the following views and controls (several of which are referenced in the sections below):

* [`UIActivityIndicatorView`](https://developer.apple.com/documentation/uikit/uiactivityindicatorview)

* [`UIAlertController`](https://developer.apple.com/documentation/uikit/uialertcontroller)

* [`UIButton`](https://developer.apple.com/documentation/uikit/uibutton)

* [`UIDatePicker`](https://developer.apple.com/documentation/uikit/uidatepicker)

* [`UIPickerView`](https://developer.apple.com/documentation/uikit/uipickerview)

* [`UIColorPickerViewController`](https://developer.apple.com/documentation/uikit/uicolorpickerviewcontroller)

* [`UIColorWell`](https://developer.apple.com/documentation/uikit/uicolorwell)

* [`UIFontPickerViewController`](https://developer.apple.com/documentation/uikit/uifontpickerviewcontroller)

* [`UIImage Picker Controller`](https://developer.apple.com/documentation/uikit/uiimagepickercontroller)

* [`UIImage View`](https://developer.apple.com/documentation/uikit/uiimageview)

* [`UIPage Control`](https://developer.apple.com/documentation/uikit/uipagecontrol)

* [`UIProgress View`](https://developer.apple.com/documentation/uikit/uiprogressview)

* [`UISearch Bar`](https://developer.apple.com/documentation/uikit/uisearchbar)

* [`UISegmented Control`](https://developer.apple.com/documentation/uikit/uisegmentedcontrol)

* [`UISlider`](https://developer.apple.com/documentation/uikit/uislider)

* [`UIStack View`](https://developer.apple.com/documentation/uikit/uistackview)

* [`UIStepper`](https://developer.apple.com/documentation/uikit/uistepper)

* [`UISwitch`](https://developer.apple.com/documentation/uikit/uiswitch)

* [`UIText Field`](https://developer.apple.com/documentation/uikit/uitextfield)

* [`UIText Formatting
    Coordinator`](https://developer.apple.com/documentation/uikit/uitextformattingcoordinator)

* [`UIText View`](https://developer.apple.com/documentation/uikit/uitextview)

* [`UIToolbar`](https://developer.apple.com/documentation/uikit/uitoolbar)

* [`WKWeb View`](https://developer.apple.com/documentation/webkit/wkwebview)

### Add Accessibility Support to Your Views

VoiceOver and other system accessibility technologies use the information provided by views and controls to help all users navigate content. UIKit views include default accessibility support. Improve user experience by providing custom accessibility information.

In this UIKitCatalog sample, several view controllers configure the `accessibility
Type` and `accessibility
Label` properties of their associated view. Picker view columns don’t have labels, so the picker view asks its delegate for the corresponding accessibility information:

```swift
// Swift
func pickerView(_ pickerView: UIPickerView, accessibilityLabelForComponent component: Int) -> String? {

    switch ColorComponent(rawValue: component)! {
    case .red:
        return NSLocalizedString("Red color component value", comment: "")


    case .green:
        return NSLocalizedString("Green color component value", comment: "")


    case .blue:
        return NSLocalizedString("Blue color component value", comment: "")
    }
}
```


### Display a Custom Alert

`Alert Controller View Controller` demonstrates several techniques for displaying modal alerts and action sheets from an interface. The configuration process is similar for all alerts:

1.  Determine the message you want to display in the alert.

2.  Create and configure a `UIAlert Controller` object.

3.  Add handlers for actions the user may take.

4.  Present the alert controller.

The `show Simple Alert` function uses the `NSLocalized String` function to retrieve the alert messages in the user’s preferred language. The `show Simple Alert` function uses those strings to create and configure the `UIAlert
Controller` object. Although the button in the alert has the title OK, the sample uses a cancel action to ensure the alert controller applies the proper styling to the button:

```swift
// Swift
func showSimpleAlert() {
    let title = NSLocalizedString("A Short Title is Best", comment: "")
    let message = NSLocalizedString("A message should be a short, complete sentence.", comment: "")
    let cancelButtonTitle = NSLocalizedString("OK", comment: "")


    let alertController = UIAlertController(title: title, message: message, preferredStyle: .alert)


    // Create the action.
    let cancelAction = UIAlertAction(title: cancelButtonTitle, style: .cancel) { _ in
        print("The simple alert's cancel action occurred.")
    }


    // Add the action.
    alertController.addAction(cancelAction)


    present(alertController, animated: true, completion: nil)
}
```

### Customize the Appearance of Sliders

This sample demonstrates different ways to display a `UISlider`, a control you use to select a single value from a continuous range of values. Customize the appearance of a slider by assigning stretchable images for left-side tracking, right-side tracking, and the thumb. In this example, the track image is stretchable and is one pixel wide. Make the track images wider to provide rounded corners, but be sure to set these images’ `cap
Insets` property to allow for the corners.

The `configure Custom Slider` function sets up a custom slider:

```swift
// Swift
func configureCustomSlider() {
    let leftTrackImage = UIImage(named: "slider_blue_track")
    customSlider.setMinimumTrackImage(leftTrackImage, for: .normal)


    let rightTrackImage = UIImage(named: "slider_green_track")
    customSlider.setMaximumTrackImage(rightTrackImage, for: .normal)


    // Set the sliding thumb image (normal and highlighted).
    let thumbImageConfig = UIImage.SymbolConfiguration(scale: .large)
    let thumbImage = UIImage(systemName: "circle.fill", withConfiguration: thumbImageConfig)
    customSlider.setThumbImage(thumbImage, for: .normal)
    let thumbImageHighlighted = UIImage(systemName: "circle", withConfiguration: thumbImageConfig)
    customSlider.setThumbImage(thumbImageHighlighted, for: .highlighted)


    customSlider.minimumValue = 0
    customSlider.maximumValue = 100
    customSlider.isContinuous = false
    customSlider.value = 84


    customSlider.addTarget(self, action: #selector(SliderViewController.sliderValueDidChange(_:)), for: .valueChanged)
}
```


### Add a Search Bar to an Interface

Use a `UISearch Bar` to receive search-related information from the user. There are various ways to customize the look of the search bar:

* Add a cancel button.

* Add a bookmark button.

* Set the bookmark image, both normal and highlighted states.

* Change the tint color that applies to key elements in the search bar.

* Set the search bar’s background image.

The `configure Search Bar` function sets up a custom search bar:

```Swift
// Swift
func configureSearchBar() {
    searchBar.showsCancelButton = true
    searchBar.showsBookmarkButton = true


    searchBar.tintColor = UIColor.systemPurple


    searchBar.backgroundImage = UIImage(named: "search_bar_background")


    // Set the bookmark image for both normal and highlighted states.
    let bookImage = UIImage(systemName: "bookmark")
    searchBar.setImage(bookImage, for: .bookmark, state: .normal)


    let bookFillImage = UIImage(systemName: "bookmark.fill")
    searchBar.setImage(bookFillImage, for: .bookmark, state: .highlighted)
}
```


### Customize the Appearance of Toolbars

This sample shows how to customize a `UIToolbar`, a specialized view that displays one or more buttons along the bottom edge of an interface. Customize a toolbar by determining its bar style (black or default), translucency, tint color, and background color.

The following `view Did Load` function in `Custom Toolbar View Controller` sets up a tinted tool bar:

    ```swift
    // swift 
    override func viewDidLoad() {
        super.viewDidLoad()


        // See the `UIBarStyle` enum for more styles, including `.Default`.
        toolbar.barStyle = .black
        toolbar.isTranslucent = false


        toolbar.tintColor = UIColor.systemGreen
        toolbar.backgroundColor = UIColor.systemBlue


        let toolbarButtonItems = [
            refreshBarButtonItem,
            flexibleSpaceBarButtonItem,
            actionBarButtonItem
        ]
        toolbar.setItems(toolbarButtonItems, animated: true)
    }
    ```


`Custom Toolbar View Controller` demonstrates further customization by changing the toolbar’s background image:

    ```swift
    //Swift
    override func viewDidLoad() {
        super.viewDidLoad()


        let toolbarBackgroundImage = UIImage(named: "toolbar_background")
        toolbar.setBackgroundImage(toolbarBackgroundImage, forToolbarPosition: .bottom, barMetrics: .default)


        let toolbarButtonItems = [
            customImageBarButtonItem,
            flexibleSpaceBarButtonItem,
            customBarButtonItem
        ]
        toolbar.setItems(toolbarButtonItems, animated: true)
    }
    ```


### Add a Page Control Interface

Use a `UIPage Control` to structure an app’s user interface. A page control is a specialized control that displays a horizontal series of dots, each of which corresponds to a page in the app’s document or other data-model entity. Customize a page control by setting its tint color for all the page-indicator dots, and for the current page-indicator dot.

The `configure Page Control` function sets up a customized page control:


    ```swift
    // Swift
    func configurePageControl() {
        // The total number of available pages is based on the number of available colors.
        pageControl.numberOfPages = colors.count
        pageControl.currentPage = 2


        pageControl.pageIndicatorTintColor = UIColor.systemGreen
        pageControl.currentPageIndicatorTintColor = UIColor.systemPurple

        pageControl.addTarget(self, action: #selector(PageControlViewController.pageControlValueDidChange), for: .valueChanged)
    }
    ```

### Add Menus to Your Controls

Attach menus to controls like `UIButton` and `UIBar Button Item`. Create menus with the [`UIAction`](https://developer.apple.com/documentation/uikit/uiaction) class, and attach a menu to each control by setting the [`UIMenu`](https://developer.apple.com/documentation/uikit/uimenu) property.

Attach a menu to a `UIButton` as shown here:


    ```swift
    // Swift
    func configureMenuButton() {
        let buttonTitle = NSLocalizedString("Button", comment: "")
        menuButton.setTitle(buttonTitle, for: .normal)


        let items = (1...5).map {
            UIAction(title: String(format: NSLocalizedString("ItemTitle", comment: ""), $0.description), handler: menuHandler)
        }
        menuButton.menu = UIMenu(title: NSLocalizedString("ChooseItemTitle", comment: ""), children: items)
        menuButton.showsMenuAsPrimaryAction = true
    }
    ```

Create a `UIBar Button Item` with a menu attached as shown here:

    ```swift
    var customTitleBarButtonItem: UIBarButtonItem {
        let buttonMenu = UIMenu(title: "",
                                children: (1...5).map {
                                   UIAction(title: "Option \($0)", handler: menuHandler)
                                })
        return UIBarButtonItem(image: UIImage(systemName: "list.number"), menu: buttonMenu)
    }
    ```

### Support Mac Catalyst

This sample app is built with Mac Catalyst, which means the sample runs on both iPad and Mac. This is achieved by selecting the Mac checkbox in Project Settings. For more about how Mac Catalyst works see [Mac Catalyst](https://developer.apple.com/mac-catalyst/).

When built for Mac Catalyst, this sample achieves:

* Interface Optimization for Mac — With Optimize Interface For the Mac project setting turned on, the app has full control of every pixel on the screen, and the app can adopt more controls specific to Mac. Building the sample for Mac Catalyst makes the app take advantage of the system features in macOS.  The option Show Designed for iPad Run Destination allows this sample, as an iPad app, to run “as-is” on Apple silicon Macs. This requires macOS 11 and a Mac with Apple silicon.

* Navigation and title bar hiding — The sample app hides these to make the app appear more like a Mac app. It also changes other behaviors by using traitCollection’s `user Interface Idiom` or the compilation conditional block that uses the `target Environment():` platform condition.

* Translucent background — By setting the split view controller’s `primary Background Style` to `.sidebar`, the primary view controller or side bar shows a blurred desktop behind its view. Setting this property has no effect when running in iOS.