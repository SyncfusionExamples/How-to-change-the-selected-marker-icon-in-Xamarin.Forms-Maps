# How to change the default marker icon with a custom view when selecting a marker in Xamarin.Forms Maps (SfMaps)

This article explains how to change the default marker icon with desired view on its selection in Syncfusion Xamarin.Forms Maps control as shown in below.

![](output.gif)

Above UI customization has been achieved with the help of CustomView property from MarkerSelected event as shown in below

[XAML]

```
    <ContentPage.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="selectedMarker">
                <StackLayout >
                    <Image Source="pin.png" Scale="1" Aspect="AspectFit "  
                           HorizontalOptions="StartAndExpand" VerticalOptions="Center"   
                           HeightRequest="15" WidthRequest="23"   />
                </StackLayout>
            </DataTemplate>
        </ResourceDictionary>
    </ContentPage.Resources>
    <maps:SfMaps x:Name="Map" >
        <maps:SfMaps.Layers >
            <maps:ImageryLayer MarkerSelected="Layer_MarkerSelected" ResetOldSelectedView="True">
                <maps:ImageryLayer.MarkerSettings>
                    <maps:MapMarkerSetting IconColor="Red" IconSize="13" MarkerIcon="Diamond"/>
                </maps:ImageryLayer.MarkerSettings>
                <maps:ImageryLayer.Markers>
                    <maps:MapMarker  Label="United States" 
                                   Latitude="40" Longitude= "-101"/>
                    <maps:MapMarker Label="Brazil"
                                    Latitude="-15.7833" Longitude= "-52" />
                    <maps:MapMarker Label="Congo" 
                                    Latitude="-1.6" Longitude= "24.4" />
                    <maps:MapMarker Label="Kazakhstan"
                                    Latitude="49.9" Longitude= "72.23" />
                    <maps:MapMarker Label="Australia" 
                                    Latitude="-20.54" Longitude= "134.10" />
                </maps:ImageryLayer.Markers>
            </maps:ImageryLayer>
        </maps:SfMaps.Layers>
    </maps:SfMaps>
```
[C#]

```
             
        private void Layer_MarkerSelected(object sender, MarkerSelectedEventArgs e)
        {
            e.CustomView = this.Resources["selectedMarker"] as DataTemplate;
        }

```

## See also

[How to customize the bubble marker in Xamarin.Forms Maps (SfMaps)](https://help.syncfusion.com/xamarin/maps/bubblemarker#customizing-bubble-marker)

[How to customize the data labels in Xamarin.Forms Maps (SfMaps)](https://help.syncfusion.com/xamarin/maps/datalabels#customizing-data-labels)

[How to customize the legend in Xamarin.Forms Maps (SfMaps)](https://help.syncfusion.com/xamarin/maps/legend)

[How to customize the tooltip in Xamarin Maps (SfMaps)](https://help.syncfusion.com/xamarin/maps/tooltip)
