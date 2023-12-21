# ADR Reversal Indicator MT5

The ADR Reversal Indicator MT5 is a trading indicator that helps identify potential reversal points in the market based on the Average Daily Range (ADR). It provides visual representation of the ADR range through horizontal lines on the chart and generates alerts when the price exceeds the ADR range.

## How it works
The indicator calculates the ADR for a specified period (default: 14) by summing up the difference between the high and low prices of each bar within the period and dividing it by the number of bars. It then plots two lines on the chart representing the upper and lower ADR range.

The `OnCalculate` function is the main function that is called on each new tick to calculate and update the indicator values. It loops through the available bars and calculates the ADR for each bar using the `CalculateADR` function. It also updates the upper and lower ADR buffers to be used for plotting the lines on the chart.

The `CalculateADR` function calculates the ADR for a given index by summing up the difference between the high and low prices of the previous `ADR_Period` bars and dividing it by `ADR_Period`.

The `GenerateAlerts` function is responsible for generating alerts when the price exceeds the ADR range. It compares the current price with the upper and lower ADR values and triggers an alert if the price exceeds either range. Additional code can be added to send email or push notifications when an alert is triggered.

The `DrawADRRange` function is used to draw the horizontal lines representing the upper and lower ADR range on the chart. It first deletes any existing lines and then creates new lines using the `ObjectCreate` function. The color of the lines can be customized by setting the `OBJPROP_COLOR` property.

The `OnInit` function is called when the indicator is initialized. It sets the indicator properties such as style, labels, and draw begin index. It also sets the indicator digits based on the market info.

The `OnDeinit` function is called when the indicator is removed from the chart. It deletes the ADR range lines created by the `DrawADRRange` function.

## Product Description
The ADR Reversal Indicator MT5 is a powerful tool for traders who want to boost their forex trading with instant alerts based on the Average Daily Range. It helps identify potential reversal points in the market, allowing traders to enter or exit positions with greater confidence.

Key Features:
- Calculates and plots the upper and lower ADR range on the chart
- Generates alerts when the price exceeds the ADR range
- Customizable ADR period
- Easy to use and interpret

With the ADR Reversal Indicator MT5, traders can stay informed about price movements within the ADR range and take advantage of potential reversal opportunities. It is suitable for both beginner and experienced traders who want to enhance their trading strategy.

Please note that ForexRobotEasy is not the official developer of this product. We provide this sample code as an example of how the ADR Reversal Indicator MT5 can work. To find the official developer of this product and access detailed reviews and trading results, please visit [forexroboteasy.com](https://forexroboteasy.com/forex-robot-review/review-adr-reversal-indicator-mt5-boost-your-forex-trading-with-instant-alerts/).
