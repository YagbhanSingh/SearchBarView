# 🔍 SearchBarView – Customizable UIKit Search Bar in Swift

`SearchBarView` is a fully customizable and reusable UIKit-based search bar component written in Swift. It allows iOS developers to integrate a feature-rich search interface into their apps with minimal setup. Designed for flexibility and style, it supports advanced UI styling, tap actions, debounce handling, and more.

## ✨ Features

* Custom placeholder text, font, and color
* Optional cancel button with animation
* Configurable height and paddings
* Border styling and background customization
* Left and right icon support with tap actions
* Built-in debounce handling for efficient search
* Public methods to control and access state

## 📸 Preview

> *(Include a screenshot or GIF here if you have one)*

## 📦 Installation

Copy `SearchBarView.swift` to your project. No external dependencies required.

## 🛠️ Usage

### 1. Add the View

```swift
let searchBar = SearchBarView(
    placeholder: "Search users",
    showCancelButton: true,
    backgroundColor: .white,
    searchTextFieldColor: .systemGray6,
    borderColor: .lightGray,
    cornerRadius: 12,
    addShadow: true,
    height: 48,
    padding: UIEdgeInsets(top: 8, left: 16, bottom: 8, right: 16),
    placeholderFont: UIFont.systemFont(ofSize: 14),
    placeholderTextColor: .darkGray,
    leftIcon: UIImage(systemName: "magnifyingglass"),
    rightIcon: UIImage(systemName: "mic"),
    onLeftIconTap: {
        print("Left icon tapped")
    },
    onRightIconTap: {
        print("Right icon tapped")
    }
)
searchBar.delegate = self
view.addSubview(searchBar)

// Add layout constraints or frame manually
```

### 2. Implement the Delegate

```swift
extension YourViewController: SearchBarViewDelegate {
    func searchBarView(_ searchBarView: SearchBarView, didChangeText text: String) {
        print("Search Text: \(text)")
    }

    func searchBarViewDidCancel(_ searchBarView: SearchBarView) {
        print("Search cancelled")
    }
}
```

## 🔧 Public API

```swift
func setText(_ text: String)
func getText() -> String
func clearText()
func become()   // Focus textfield
func resign()   // Remove focus
func setCancelButtonVisible(_ visible: Bool, animated: Bool = true)
```

## ⏳ Debounce

Search text changes are debounced (default: `0.3s`) to avoid frequent firing. You can customize it:

```swift
SearchBarView(debounceInterval: 0.5)
```

## 📌 Customizations

| Property                          | Description                  |
| --------------------------------- | ---------------------------- |
| `placeholder`                     | Placeholder string           |
| `showCancelButton`                | Shows or hides cancel button |
| `padding`                         | Outer padding (UIEdgeInsets) |
| `backgroundColor`                 | Search view background       |
| `searchTextFieldColor`            | Text field background color  |
| `borderColor`                     | Border color                 |
| `borderWidth`                     | Border width                 |
| `cornerRadius`                    | Corner radius for text field |
| `height`                          | Overall height               |
| `placeholderFont`                 | Custom placeholder font      |
| `placeholderTextColor`            | Placeholder text color       |
| `textfieldFont`                   | Main text font               |
| `textfieldTextColor`              | Text field color             |
| `leftIcon` / `rightIcon`          | Icons on either side         |
| `onLeftIconTap`, `onRightIconTap` | Actions for icon taps        |

## ✅ Requirements

* iOS 13+
* Swift 5+

## 🤜 Contributions

Feel free to fork, improve or submit issues! Your feedback is welcome.

## 🧑‍💻 Author

**Your Name**
📧 [chaudharyyagh@gmail.com](mailto:chaudharyyagh@gmail.com)
🔗 [@yagbhan-singh](https://www.linkedin.com/in/yagbhan-singh/)
