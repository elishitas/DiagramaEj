# DiagramaEj

* diagrama

```mermaid
graph LR;
    orderDb[(ordersDb)]
    productWriteDb[(product write store)]
    productReadDb[(Product read store)]
    PublicApi-->CreateProduct;
    PublicApi-->UpdateProduct;
    PublicApi--> CreateOrder;
    PublicApi-->GetOrder;
    UpdateProduct-->|CQRS| ProductMs;
    CreateProduct-->|CQRS| ProductMs;
    SubscriptionMs-->EmailMs;
    CreateOrder-->|Event sourcing|OrderMs;
    GetOrder-->OrderMs;
    OrderMs-->ProductMs;
    OrderMs-->EmailMs;
    PrivateApi-->Reports;
    Reports-->OrderMs;
    ProductMs-.->|Eventual Consistency|OrderMs;
    OrderMs-->orderDb;
    ProductMs-->productWriteDb;
    ProductMs-->productReadDb;
```
* mapas

```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "id": 1,
      "properties": {
        "ID": 0
      },
      "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
              [-5.5,55.5],
              [-10.5,55.5],
              [-10.5,51],
              [-5.5,51],
              [-5.5,55.5]
          ]
        ]
      }
    }
  ]
}
```
* modelo 3d

```stl
solid cube_corner
  facet normal 0.0 -1.0 0.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 1.0 0.0 0.0
      vertex 0.0 0.0 1.0
    endloop
  endfacet
  facet normal 0.0 0.0 -1.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 0.0 1.0 0.0
      vertex 1.0 0.0 0.0
    endloop
  endfacet
  facet normal -1.0 0.0 0.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 0.0 0.0 1.0
      vertex 0.0 1.0 0.0
    endloop
  endfacet
  facet normal 0.577 0.577 0.577
    outer loop
      vertex 1.0 0.0 0.0
      vertex 0.0 1.0 0.0
      vertex 0.0 0.0 1.0
    endloop
  endfacet
endsolid
```
