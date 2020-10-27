---
layout: default
title: Styling
parent: WPF
grand_parent: .NET 5
has_children: false
has_toc: true
---

{% include toc.html %}

## Adding Styles to Element Resources

Resources can be added at the element level:

```csharp
<!-- Adding element-specifc styles. -->
<Window.Resources>
        <!-- Border -->
        <Style TargetType="Border">
            <Setter Property="BorderBrush"
                    Value="Black" />
            <Setter Property="BorderThickness"
                    Value="1" />
        </Style>

        <!-- Button -->
        <Style TargetType="Button">
            <Setter Property="Padding"
                    Value="15" />
        </Style>
</Window.Resources>
```

## Resource Dictionaries
### Creating resource dictionaries

Add a resource dictionary to the project and define the styles:

```csharp
<!-- MyResources.xaml -->
<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                    xmlns:local="clr-namespace:WpfLayout.MVVM.MainWindow">
    <!-- Border -->
    <Style TargetType="Border">
        <Setter Property="BorderBrush"
                    Value="Black" />
        <Setter Property="BorderThickness"
                    Value="1" />
    </Style>

    <!-- Button -->
    <Style TargetType="Button">
        <Setter Property="Padding"
                    Value="15" />
    </Style>
</ResourceDictionary>
```

### Adding resources using dictionaries

Add the resource dictionaries to the element's resources:

```csharp
<!-- Add a single dictionary. -->
<Window.Resources>
    <ResourceDictionary Source="MyResources.xaml" />
</Window.Resources>

<!-- Merge multiple dictionaries. -->
<Window.Resources>
    <ResourceDictionary>
        <ResourceDictionary.MergedDictionaries>
            <ResourceDictionary Source="MyResources1.xaml" />
            <ResourceDictionary Source="MyResources2.xaml" />
            <ResourceDictionary Source="MyResources3.xaml" />
        </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
</Window.Resources>
```