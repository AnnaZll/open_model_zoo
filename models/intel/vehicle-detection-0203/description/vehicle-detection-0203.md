# vehicle-detection-0203

## Use Case and High-Level Description

This is a vehicle detector that is based on ResNet18
backbone with FPN and CascadeRCNN heads.

## Example

![](./vehicle-detection-0203.png)

## Specification

| Metric                          | Value                                     |
|---------------------------------|-------------------------------------------|
| AP @ [ IoU=0.50:0.95 ]          | 0.438 (internal test set)                 |
| GFlops                          | 112.34                                    |
| MParams                         | 24.11                                    |
| Source framework                | PyTorch\*                                 |

Average Precision (AP) is defined as an area under
the [precision/recall](https://en.wikipedia.org/wiki/Precision_and_recall)
curve.

## Performance

## Inputs

Name: `input`, shape: [1x3x800x1344] - An input image in the format [BxCxHxW],
where:

- B - batch size
- C - number of channels
- H - image height
- W - image width

Expected color order is BGR.

## Outputs

The net outputs blob with shape: [1, 1, N, 5], where N is the number of detected
bounding boxes. Each detection has the format
  [`x_min`, `y_min`, `x_max`, `y_max`, `conf`], where:
  - (`x_min`, `y_min`) - coordinates of the top left bounding box corner
  - (`x_max`, `y_max`) - coordinates of the bottom right bounding box corner.
  - `conf` - confidence for the predicted class

## Legal Information
[*] Other names and brands may be claimed as the property of others.