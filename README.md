# siroman.blazor.viewer3d
![siroman.blazor.viewer3d](../main/Assets/blazor.viewer3d.jpg)

## Overview
This repository contains examples of using the 3d view component in the [ASP.NET Core Blazor](https://docs.microsoft.com/en-us/aspnet/core/blazor/) applications.

## How to install

With .NET CLI
```
dotnet add package Siroman.Blazor.Viewer3D
```
With Package Manager
```
Install-Package Siroman.Blazor.Viewer3D -Version 0.1.1
```
Or just download it from <https://www.nuget.org/packages/Siroman.Blazor.Viewer3D> and add it as project reference.

## How to use

1. Add usings to the _Imports.razor
```
...
@using Siroman.Blazor.Viewer3D
@using Siroman.Blazor.Viewer3D.Options
@using Siroman.Blazor.Viewer3D.Common;
```

2. Put the View3D component to you blazor application page and add some code
```
<View3D @ref="View3D1"/>
<br />
<button @onclick="OnLoadColladaButtonClick">Load Collada</button>


@code {
    private View3D View3D1;

    private async Task OnLoadColladaButtonClick()
    {
       await View3D1.LoadCollada("https://threejs.org/examples/models/collada/elf/elf.dae");
        await View3D1.SetCameraPosition(new Position()
        {
            Y = 5,
            Z = 10
        });
    }
}
```


