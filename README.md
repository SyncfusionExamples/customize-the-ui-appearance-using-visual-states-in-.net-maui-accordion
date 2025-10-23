# Customize-the-UI-appearance-using-visual-states-in-.net-maui-accordion

This sample demonstrates how to customize the UI appearance of the Syncfusion SfAccordion control in a .NET MAUI app using Visual State Manager (VSM). It shows how to define visual states such as "Expanded" and "Collapsed" for `AccordionItem` and apply property setters (for example header background and icon color) that update automatically when the state changes.

For a full getting-started guide to the SfAccordion control, see the Syncfusion user guide: [Getting Started with Xamarin Accordion (SfAccordion)](https://help.syncfusion.com/xamarin/accordion/getting-started)

## Overview

- Control: Syncfusion `SfAccordion` for .NET MAUI
- Topic: Customize UI appearance with Visual State Manager (VSM)
- Key idea: Define `VisualStateGroupList` for `AccordionItem` and set properties in `Expanded` and `Collapsed` states so the header visuals update automatically when the item expands or collapses.

## XAML (Visual States)

Below is the VisualStateGroup definition for `syncfusion:AccordionItem`, which defines two states: `Expanded` and `Collapsed`. Each state specifies the header background and the header icon color.

```
<ContentPage.Resources>
    <Style TargetType="syncfusion:AccordionItem">
        <Setter Property="VisualStateManager.VisualStateGroups">
            <VisualStateGroupList>
                <VisualStateGroup>
                    <VisualState Name="Expanded">
                        <VisualState.Setters>
                            <Setter Property="HeaderBackground" Value="#6750A4"/>
                            <Setter Property="HeaderIconColor" Value="White"/>
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="Collapsed">
                        <VisualState.Setters>
                            <Setter Property="HeaderBackground" Value="#1F1C1B1F"/>
                            <Setter Property="HeaderIconColor" Value="#49454F"/>
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>
        </Setter>
    </Style>
</ContentPage.Resources>
```

This style ensures every `AccordionItem` in the page inherits the Visual State definitions. When an item toggles between expanded and collapsed, the VSM applies the corresponding setters so the header background and icon color transition to the specified values.

## How it works

- Visual State Manager (VSM) groups visual states and makes it easy to switch UI property values based on state names such as `Expanded` or `Collapsed`.
- By defining the VSM at the `AccordionItem` style level, every item uses the same behavior — no need to duplicate state logic for each header.
- `HeaderIconColor` is a bindable property on the `AccordionItem` that is set by the VSM; downstream UI elements (like `Label`) can bind to it using `x:Reference` to the item to pick up the current color.

##### Conclusion
I hope you enjoyed learning about how to customize the appearance of .NET MAUI SfAccordion using “Expanded” and “Collapsed” visual states.

You can refer to our  [Xamarin.Forms Accordion feature tour](https://www.syncfusion.com/xamarin-ui-controls/xamarin-accordion) page to know about its other groundbreaking feature representations and [documentation](https://help.syncfusion.com/xamarin/accordion/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Xamarin.Forms Accordion example](https://www.syncfusion.com/demos/xamarin) to understand how to create and manipulate data.

For current customers, you can check out our Document Processing Libraries from the [License and Downloads](https://www.syncfusion.com/account/login) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads) to check out our controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums) or [Direct-trac](https://support.syncfusion.com/create). We are always happy to assist you!
