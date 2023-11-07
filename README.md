# How-to-add-custom-axis-label-in-Blazor-chart
 
Axis label in [Blazor Chart](https://www.syncfusion.com/blazor-components/blazor-charts) has been generated based on the provided data points. The charts support you to change the entire text with your desired text.

We can add the custom label to the axis label in blazor chart using [OnAxisLabelRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartEvents.html#Syncfusion_Blazor_Charts_ChartEvents_OnAxisLabelRender) event. This event triggers before each axis label are rendered. 

This event contains the following arguments.

•	[LabelStyle](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_LabelStyle) – Specifies the font information of the axis label.

•	[Text](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_Text) – Specifies the text to be displayed in the axis label.

•	[Value](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_Value) – Specifies the value of the axis label.

We can add custom label to the axis label in blazor chart by using the [Text](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_Text) property  in the [OnAxisLabelRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartEvents.html#Syncfusion_Blazor_Charts_ChartEvents_OnAxisLabelRender) event. 

The following code example illustrates this.

**C#**

```cshtml

@using Syncfusion.Blazor.Charts

<SfChart Width="600">
    <ChartEvents OnAxisLabelRender="AxisLabelEvent"></ChartEvents>
    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Line">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code {
    public class SalesInfo
    {
        public string Month { get; set; }
        public double SalesValue { get; set; }
    }

    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 10 },
        new SalesInfo { Month = "Feb", SalesValue = 12 },
        new SalesInfo { Month = "Mar", SalesValue = 20 },
        new SalesInfo { Month = "Apr", SalesValue = 28 },
        new SalesInfo { Month = "May", SalesValue = 35 },
        new SalesInfo { Month = "Jun", SalesValue = 40 },
        new SalesInfo { Month = "Jul", SalesValue = 50 }
    };

    public void AxisLabelEvent(AxisLabelRenderEventArgs args)
    {             
        if(args.Axis.Name == "PrimaryYAxis")
        {
            if(args.Value < 20)
            {
                args.Text = "low";
            }
            if (args.Value >= 20 && args.Value <= 30)
            {
                args.Text = "average";
            }
            if(args.Value > 30)
            {
                args.Text = "high";
            }
        }
    }
}

```

The following screenshot illustrate the output of the above code snippet.

**Output:**

![](/Axis-label-text-customization.png)

**Conclusion**

I hope you enjoyed learning how to add custom axis label in Blazor Chart Component.

You can refer to our [Blazor Chart feature tour](https://www.syncfusion.com/blazor-components/blazor-charts) page to know about its other groundbreaking feature representations and [documentation](https://blazor.syncfusion.com/documentation/chart/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Blazor Chart example](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap5) to understand how to create and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/blazor) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [Direct-Trac](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/blazor-components?control=charts). We are always happy to assist you!


