## Representing YAML.

```
CellName: 101JP00000BP6.000
Comment: Author JP | Tester Shyam v7
Edition: 5

# you can add global offset parameters too.
xoffset: 7.5
yoffset: 7.5

Points:
  - Name: P1
    Location: -0.5,-0.5

  - Name: P2
    Location: 0.1520994,-0.0916024

Curves:

  - Name: curve2
    Start: P2
    Vertices: 0.1520994,-0.0916024 , 0.0718937,-0.0031705 , -0.0185947,-0.0484147 , -0.0175664,-0.1286204 , 0.0050557,-0.1697515 , 0.0718937,-0.1841474 , 0.1233076,-0.1707798 , 0.1449015,-0.1347901 , 0.1520994,-0.0916024

  - Name: curve1
    Start: P1
    Vertices: -0.5,-0.5 , -0.5,0.5 , 0.5,0.5 ,  0.5,-0.5 , -0.5,-0.5

Surfaces:

  - Name: S2
    Exterior: curve1

  - Name: S3
    Exterior: Rcurve2

  - Name: S4
    Exterior: curve1
    Interior:
      - Hole: curve2

Features:

  - Name: DataCoverage
    Foid: 1810:608:68
    Prim: Surface
    Attributes:
      - Name: maximumDisplayScale
        Value: 90000
      - Name: minimumDisplayScale
        Value: 180000
    Geometry: S2

  - Name: NavigationalSystemOfMarks  # Data Cov
    Foid: 1810:4081:100
    Prim: Surface
    Attributes:
      - Name: marksNavigationalSystemOf
        Value: IALA A
    Geometry: S2

  - Name: DepthArea
    Foid: 1810:1411:99
    Prim: Surface
    Attributes:
      - Name: depthRangeMaximumValue
        Value: 20
      - Name: depthRangeMinimumValue
        Value: 1000
    Geometry: S4                       # External Surface with hole
```
Header information
```
  - Name: LandArea
    Foid: 1810:2204:2001
    Prim: Surface
    Attributes:
      - Name: featureName
        id: 1
      - Name: language
        Value: eng
        parent: 1
      - Name: name
        Value: Null Island
        parent: 1
      - Name: displayName
        Value: 1
        parent: 1
    Geometry: S3

  - Name: Coastline
    Foid: 1810:1234:12
    Prim: Curve
    Attributes:
      - Name: categoryOfCoastline
        Value: Mangrove
    Geometry: curve2
```
