# How to Add Custom Axis Labels in a Syncfusion Blazor Chart

## Overview

This sample demonstrates how to customize axis label text in a Syncfusion [Blazor Charts](https://www.syncfusion.com/blazor-components/blazor-charts) using the `OnAxisLabelRender` event. Instead of displaying the default numeric axis values, the application intercepts axis label rendering and replaces numeric ranges with meaningful labels such as "low", "average", and "high".

This approach is useful when business users need qualitative or domain-specific labels instead of raw numeric values. The customization occurs dynamically during the chart rendering lifecycle without modifying the underlying data source.

## Key Features

- Uses the `SfChart` component to render chart data.
- Handles the `OnAxisLabelRender` event through `ChartEvents`.
- Uses `AxisLabelRenderEventArgs.Text` to replace the displayed axis label text.
- Uses `AxisLabelRenderEventArgs.Value` to determine which custom label should be rendered.
- Checks `args.Axis.Name` to apply customization only to the intended axis (`PrimaryYAxis`).
- Displays charted data using a `ChartSeries` configured with:
  - `DataSource`
  - `XName`
  - `YName`
  - `Type="ChartSeriesType.Line"`
- Uses a categorical X-axis through `ChartPrimaryXAxis` with `ValueType="ValueType.Category"`.

## Prerequisites

- [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) or [Visual Studio Code](https://code.visualstudio.com/)
- [.NET SDK](https://dotnet.microsoft.com/en-us/download/dotnet) compatible with the project's target framework

## How to Run the Project

**Visual Studio 2022**

1. Clone or download this repository.
2. Open the project file:

   `AddCustomAxisLabel.csproj`

3. Restore NuGet packages.
4. Build the project.
5. Run the application using `Ctrl+F5`.

**Visual Studio Code**

1. Clone or download this repository.
2. Open the repository folder in Visual Studio Code.
3. Open the integrated terminal.
4. Navigate to the project directory:

```bash
cd AddCustomAxisLabel
dotnet restore
dotnet run
```

5. Open the URL displayed in the terminal after the application starts.

## Project Structure

- `AddCustomAxisLabel/Pages/Index.razor` - Hosts the Syncfusion chart and implements custom axis label rendering through `OnAxisLabelRender`.

## Support and Feedback

- For general product questions, visit the [Syncfusion Community Forum](https://www.syncfusion.com/forums) or [Syncfusion Support](https://www.syncfusion.com/support).
- To report an issue specific to this sample, open a GitHub issue in this repository.
- Official documentation for axis label customization using `OnAxisLabelRender`: https://help.syncfusion.com/chart-sdk/blazor/charts/axis-customization

## License

This is a Syncfusion sample project provided to demonstrate product usage. Review the [Syncfusion license terms](https://www.syncfusion.com/sales/pricing?category=ui-components) before using Syncfusion components in your own applications.