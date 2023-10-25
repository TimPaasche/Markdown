# WPF Encyclopedia

[[TOC]]

## use of data templates by analyzing the datemtype in an enumerable

In this example, we've defined a DataTemplate with the key "ItemTemplate" in the Window's resources. The TabControl's ContentTemplate is set to this DataTemplate, which will be used to display the content of each tab. The ItemTemplate for tab headers is also defined within the TabControl itself.

### View (xaml)

```xml
<Window x:Class="WpfTabControlExample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="clr-namespace:WpfTabControlExample"
        Title="TabControl Example" Height="350" Width="500">
    <Window.Resources>
        <!-- DataTemplate for ItemTypeA -->
        <DataTemplate x:Key="ItemTypeATemplate">
            <StackPanel>
                <TextBlock Text="{Binding Name}" FontSize="18" />
                <TextBlock Text="{Binding Description}" Margin="0,5,0,0" />
            </StackPanel>
        </DataTemplate>

        <!-- DataTemplate for ItemTypeB -->
        <DataTemplate x:Key="ItemTypeBTemplate">
            <StackPanel>
                <TextBlock Text="{Binding Title}" FontSize="18" />
                <TextBlock Text="{Binding Content}" Margin="0,5,0,0" />
            </StackPanel>
        </DataTemplate>

        <!-- DataTemplateSelector -->
        <local:ItemDataTemplateSelector x:Key="ItemDataTemplateSelector"
            ItemTypeATemplate="{StaticResource ItemTypeATemplate}"
            ItemTypeBTemplate="{StaticResource ItemTypeBTemplate}" />
    </Window.Resources>

    <Grid>
        <TabControl Name="tabControl" ItemsSource="{Binding Items}">
            <TabControl.ItemTemplate>
                <DataTemplate>
                    <TextBlock Text="{Binding Header}" />
                </DataTemplate>
            </TabControl.ItemTemplate>
            <TabControl.ContentTemplateSelector>
                <StaticResource ResourceKey="ItemDataTemplateSelector" />
            </TabControl.ContentTemplateSelector>
        </TabControl>
    </Grid>
</Window>
```

### Code Behind (xaml.cs)

```c#
using System.Collections.ObjectModel;
using System.Windows;

namespace WpfTabControlExample {
    public partial class MainWindow : Window {
        public ObservableCollection<object> Items { get; set; } = new ObservableCollection<object>();

        public MainWindow() {
            InitializeComponent();

            Items.Add(new ItemTypeA { Header = "Tab A", Name = "Name", Description = "This is the description of this Tab" });
            Items.Add(new ItemTypeB { Header = "Tab B", Title = "Title", Content = "This is the content of this Tab" });

            DataContext = this;
        }
    }
}
```

### Data Classes (C#)

**Data Class A:**

```c#
namespace WpfTabControlExample {
    public class ItemTypeA {

        public string Header { get; set; }
        public string Name { get; set; }
        public string Description { get; set; }
    }
}
```

**Data Class B:**

```c#
namespace WpfTabControlExample {
    public class ItemTypeB {
        public string Header { get; set; }
        public string Title { get; set; }
        public string Content { get; set; }
    }
}
```
