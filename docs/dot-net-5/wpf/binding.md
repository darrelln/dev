---
layout: default
title: Data Binding
parent: WPF
grand_parent: .NET 5
has_children: false
has_toc: true
---

{% include toc.html %}

## Setting a view model
You can do this either in XAML:
```xml
// Using XAML.
<Window ..., xmlns:viewmodels="clr-namespace:MyApp.MVVM.ViewModels">
    <Window.DataContext>
        <local:MyViewModel>
    </Window.DataContext>
    ...
```

Or the code-behind:
```csharp
// Using the code behind.
public MainWindow()
{
    InitilializeComponent();
    DataContext = new MyViewModel();
}
```

## Binding width and height to control by name

```xml
<Border x:Name="tabPanelBorder">
    <TabPanel>
        <TabControl Width="{Binding ActualWidth, ElementName=tabPanelBorder}"
                    Height="{Binding ActualHeight, ElementName=tabPanelBorder}"
...
```