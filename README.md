# Binding ExpandoObject and DynamicObject to a Blazor DataGrid

## Overview

This sample demonstrates how to bind dynamic data sources to the Syncfusion [Blazor DataGrid](https://www.syncfusion.com/blazor-components/blazor-datagrid) using both `DynamicObject` and `ExpandoObject` implementations. The primary sample uses a custom `OrderDetails` class that inherits from `DynamicObject`, enabling runtime member creation and retrieval without requiring a strongly typed model. The project also includes an alternative `ExpandoObject` implementation that can be used to generate grid data dynamically. This approach is useful when working with data structures whose schema is not known at compile time or may change dynamically at runtime.

## Key Features

- Uses the Syncfusion `SfGrid` component for displaying dynamic data.
- Binds the grid using the `DataSource` property.
- Defines grid columns for `OrderID`, `CustomerID`, `OrderDate`, and `Freight`.
- Uses `GridColumn.Field` values that map to dynamically generated runtime properties.
- Implements a custom `OrderDetails` class that inherits from `DynamicObject`.
- Overrides `TryGetMember(GetMemberBinder binder, out object result)` to retrieve runtime values.
- Overrides `TrySetMember(SetMemberBinder binder, object value)` to create and update runtime properties.
- Overrides `GetDynamicMemberNames()` to expose available dynamic fields.
- Stores dynamic values internally using `Dictionary<string, object>`.
- Generates sample records in `OnInitialized()` using `Enumerable.Range(...)`.
- Includes an alternative `ExpandoObject` data-binding implementation within the source code.
- Uses `EditType.DatePickerEdit` for the `OrderDate` column.
- Configures `ColumnType.Date` and date formatting using `Format="d"`.
- Configures numeric formatting using `Format="C2"` for the `Freight` column.
- Demonstrates runtime data binding without requiring a predefined model class structure.

## Prerequisites

- Visual Studio 2022 or Visual Studio Code
- .NET SDK compatible with the project's target framework

## How to Run the Project

**Visual Studio 2022**

1. Clone or download this repository.
2. Open the solution file:  `ExpandoDynamicObject.sln`
3. Restore all NuGet packages.
4. Build the solution.
5. Set the startup project according to your preferred launch profile if prompted.
6. Run the application using `Ctrl+F5`.
7. Open the local URL displayed by the application after startup.
8. View the DataGrid displaying dynamically generated data.

**Visual Studio Code**

1. Open the repository folder in Visual Studio Code.
2. Open the integrated terminal.
3. Navigate to the repository root containing the solution.

```bash
dotnet restore
dotnet run --project Client
```

4. Open the local URL displayed in the terminal after the application starts.
5. Review the DataGrid populated with dynamically generated records.

## Project Structure

`Client/Pages/Index.razor` — contains the `SfGrid`, column definitions, dynamic data generation logic, `OrderDetails : DynamicObject` implementation, and alternative `ExpandoObject` binding example.

## Support and Feedback

- For general product questions, visit the [Syncfusion Community Forum](https://www.syncfusion.com/forums) or [Syncfusion Support](https://www.syncfusion.com/support).
- To report an issue specific to this sample, open a GitHub issue in this repository.
- For official documentation related to DynamicObject and ExpandoObject data binding, visit https://help.syncfusion.com/grid-sdk/blazor/data-grid/data-binding/local-data#expandoobject-binding, https://help.syncfusion.com/grid-sdk/blazor/data-grid/data-binding/local-data#dynamicobject-binding

## License

This is a Syncfusion sample project provided to demonstrate product usage. Review the [Syncfusion license terms](https://www.syncfusion.com/sales/pricing?category=ui-components) before using Syncfusion components in your own applications.
