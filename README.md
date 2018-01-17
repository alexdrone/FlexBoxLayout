# FlexboxLayout
[![Swift](https://img.shields.io/badge/swift-3-orange.svg?style=flat)](#)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![Platform](https://img.shields.io/badge/platform-iOS%7CmacOS%20-lightgrey.svg?style=flat)](#)
[![Build](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://opensource.org/licenses/MIT)

Port of Facebook's [css-layout](facebook css layout) to Swift + *UIView* extension.


![GitHub Logo](doc/cell.jpg)
TL;DR
This layout and style is expressed in code in the following declarative fashion:


```swift

let view =  UIView().define(children: [
      UIView().define { view in
        view.backgroundColor = UIColor.d
        view.layer.cornerRadius = 24.0
        view.useFlexbox = true
        view.layout_width = 48
        view.layout_height = 48
        view.layout_marginAll = 16
        view.layout_alignSelf = .center
        view.layout_justifyContent = .flexStart
      },
      UIView().define(children: [
        UILabel().define { view in
          view.text = "TITLE"
          view.useFlexbox = true
          view.layout_alignSelf = .flexStart
        },
        UILabel().define { view in
          view.text = "SUBTITLE"
          view.useFlexbox = true
          view.layout_alignSelf = .flexStart
        }
      ]) { view in
        view.backgroundColor = UIColor.a
        view.useFlexbox = true
        view.layout_alignSelf = .center
        view.layout_flexGrow = 0.8
        view.layout_paddingAll = 8
      },
      UILabel().define { view in
        view.text = "88:88"
        view.textColor = UIColor.f
        view.textAlignment = .center
        view.font = UIFont.systemFont(ofSize: 12, weight: UIFontWeightLight)
        view.useFlexbox = true
        view.layout_minWidth = 64
        view.layout_alignSelf = .center
        view.layout_flexShrink = 0.2
        view.layout_paddingAll = 8
        view.layout_marginAll = 2

      }
    ]) { view in
      view.backgroundColor = UIColor.white
      view.layer.borderColor = UIColor.b.cgColor
      view.layer.borderWidth = 2.0
      view.useFlexbox = true
      view.layout_justifyContent = .center
      view.layout_alignSelf = .stretch
      view.layout_marginAll = 8
      view.layout_flexDirection = .row
      view.layout_maxWidth = self.view.bounds.width - 40
    }

view.render()

```

The  `define` function stores the configuration closure for each view and these are recursively re-applied whenever the `render` function is called on the root view.



 
