## ConversionOptions

### PDFOptions
| Field             | Type    | Description                                                 | Note     |
|-------------------|---------|-------------------------------------------------------------|----------|
| **width**         | Float   | Width in inches                                             | Optional |
| **height**        | Float   | Height in inches                                            | Optional |
| **left_margin**   | Float   | Left margin in inches                                       | Optional |
| **right_margin**  | Float   | Right margin in inches                                      | Optional |
| **top_margin**    | Float   | Top margin in inches                                        | Optional |
| **bottom_margin** | Float   | Bottom margin in inches                                     | Optional |
| **jpeg_quality**  | Integer | Quality in percent                                          | Optional |
| **background**    | String  | CSS background like '#FF0000'. For conversion from SVG only | Optional |

### ImageOptions

-  for JPEG, BMP, PNG, TIFF, GIF, WEBP formats

| Field             | Type    | Description                                                                                    | Note     |
|-------------------|---------|------------------------------------------------------------------------------------------------|----------|
| **width**         | Integer | Width in pixel                                                                                 | Optional |
| **height**        | Integer | Height in pixel                                                                                | Optional |
| **left_margin**   | Integer | Left margin in pixel                                                                           | Optional |
| **right_margin**  | Integer | Right margin in pixel                                                                          | Optional |
| **top_margin**    | Integer | Top margin in pixel                                                                            | Optional |
| **bottom_margin** | Integer | Bottom margin in pixel                                                                         | Optional |
| **resolution**    | Integer | Output DPI (horizontal and vertical). Default 96. Higher values produce larger pixel dimensions. | Optional |
| **background**    | String  | CSS background like '#FF0000'. For conversion from SVG only                                    | Optional |

### XPSOptions
| Field             | Type   | Description                                                 | Note     |
|-------------------|--------|-------------------------------------------------------------|----------|
| **width**         | Float  | Width in inches                                             | Optional |
| **height**        | Float  | Height in inches                                            | Optional |
| **left_margin**   | Float  | Left margin in inches                                       | Optional |
| **right_margin**  | Float  | Right margin in inches                                      | Optional |
| **top_margin**    | Float  | Top margin in inches                                        | Optional |
| **bottom_margin** | Float  | Bottom margin in inches                                     | Optional |
| **background**    | String | CSS background like '#FF0000'. For conversion from SVG only | Optional |

### DocOptions
| Field             | Type  | Description                                                  | Note     |
|-------------------|-------|--------------------------------------------------------------|----------|
| **width**         | Float | Width in inches                                              | Optional |
| **height**        | Float | Height in inches                                             | Optional |
| **left_margin**   | Float | Left margin in inches                                        | Optional |
| **right_margin**  | Float | Right margin in inches                                       | Optional |
| **top_margin**    | Float | Top margin in inches                                         | Optional |
| **bottom_margin** | Float | Bottom margin in inches                                      | Optional |

### SvgOptions
| Field               | Type    | Description                                                                                             | Note     |
|---------------------|---------|---------------------------------------------------------------------------------------------------------|----------|
| **error_threshold** | Float   | This parameter defines maximum deviation of points to fitted curve. By default it is 30.                | Optional |
| **max_iterations**  | Integer | This parameter defines number of iteration for least-squares approximation method. By default it is 30. | Optional |
| **colors_limit**    | Integer | The maximum number of colors used to quantize an image. Default value is 25.                            | Optional |
| **line_width**      | Float   | The value of this parameter is affected by the graphics scale. Default value is 1.                      | Optional |


### MarkdownOptions
| Field       | Type | Description                                   | Note     |
|-------------|------|-----------------------------------------------|----------|
| **use_git** | bool | Use git flavor. True or False. Default false. | Optional |


### PdfMetadata

-  Applied only when the output format is PDF; ignored otherwise. Any field omitted or set to `nil` keeps the rendering engine default.

Pass as `:pdf_metadata` inside the `options` hash. Example:

```ruby
opts = {
  pdf_metadata: {
    title: 'Monthly Report',
    author: 'Jane Doe',
    subject: 'Q3 Results',
    keywords: 'report, q3, pdf',
    creator: 'My Application',
    producer: 'My Company',
    creation_date: '2024-01-15T10:30:00Z',
    modification_date: '2024-06-20T18:45:00Z'
  }
}

api_instance.convert_local_to_local('test.html', 'test.pdf', opts)
```

| Field                 | Type   | Description                                    | Note     |
|-----------------------|--------|------------------------------------------------|----------|
| **title**             | String | PDF `/Title`                                   | Optional |
| **author**            | String | PDF `/Author`                                  | Optional |
| **subject**           | String | PDF `/Subject`                                 | Optional |
| **keywords**          | String | PDF `/Keywords`                                | Optional |
| **creator**           | String | PDF `/Creator`                                 | Optional |
| **producer**          | String | PDF `/Producer`                                | Optional |
| **creation_date**     | String | PDF `/CreationDate`. ISO 8601 datetime string. | Optional |
| **modification_date** | String | PDF `/ModDate`. ISO 8601 datetime string.      | Optional |
