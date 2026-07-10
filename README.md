# Getting Started with .NET MAUI Digital Gauge

## Creating an application using the .NET MAUI Digital Gauge

The [.NET MAUI Digital Gauge](https://www.syncfusion.com/maui-controls/maui-digital-gauge?utm_source=github&utm_medium=listing&utm_campaign=maui-digital-gauge-github-samples) is a data visualization control used to display text and numeric values as digital characters with customizable segment styles. This guide will help you integrate the Digital Gauge control into your .NET MAUI application.

### Step 1: Create a new .NET MAUI application in Visual Studio

1. Go to **File > New > Project** and choose the **.NET MAUI App** template.
2. Name the project and choose a location. Click **Next**.
3. Select the .NET framework version and click **Create**.

### Step 2: Install the Syncfusion .NET MAUI Gauges NuGet package

1. In **Solution Explorer**, right-click the project and choose **Manage NuGet Packages**.
2. Search for Syncfusion.Maui.Gauges and install the latest version.
3. Ensure the necessary dependencies are installed correctly, and the project is restored.

### Step 3: Register the Syncfusion handler

Syncfusion.Maui.Core NuGet is a dependent package for all Syncfusion controls of .NET MAUI. In the MauiProgram.cs file, register the handler for Syncfusion core.



**[C#]**
```
using Microsoft.Maui;
using Microsoft.Maui.Hosting;
using Syncfusion.Maui.Core.Hosting;

namespace DigitalGaugeGettingStarted
{
    public static class MauiProgram
    {
        public static MauiApp CreateMauiApp()
        {
            var builder = MauiApp.CreateBuilder();
            builder
                .UseMauiApp<App>()
                .ConfigureSyncfusionCore()
                .ConfigureFonts(fonts =>
                {
                    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                });

            return builder.Build();
        }
    }
}
```

### Step 4: Add the Digital Gauge namespace

Import the Gauge namespace to your XAML or C# code.

**[XAML]**
```
xmlns:gauge="clr-namespace:Syncfusion.Maui.Gauges;assembly=Syncfusion.Maui.Gauges"
```

**[C#]**
```
using Syncfusion.Maui.Gauges;
```

### Step 5: Initialize the Digital Gauge

Initialize the [SfDigitalGauge]() and set a `Text` value to display in the digital gauge.

**[XAML]**
```
<ContentPage   
    xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:gauge="clr-namespace:Syncfusion.Maui.Gauges;assembly=Syncfusion.Maui.Gauges"
    x:Class="DigitalGaugeGettingStarted.MainPage">

    <Grid>
        <gauge:SfDigitalGauge Text="06:14:56 PM" 
                              CharacterType="FourteenSegment" />
    </Grid>
</ContentPage>
```

**[C#]**
```
using Syncfusion.Maui.Gauges;
. . .

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        this.InitializeComponent();
        
        SfDigitalGauge digitalGauge = new SfDigitalGauge()
        {
            Text = "06:14:56 PM",
            CharacterType = CharacterType.FourteenSegment
        };

        this.Content = digitalGauge;
    }
}
```

![Digital Gauge in .NET MAUI Digital Gauge](Images\getting-started.png)