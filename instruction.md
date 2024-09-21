# Note
Go to file image_classification
```python
cd truongtd/Pipedream/runtime/image_classification/
```
# Run in single machine
```python
python3 main_with_runtime.py --module models.resnet50.gpus=2 -b 128
```
# Run pipeline in two machines
```python
python3 main_with_runtime.py --module models.resnet50.gpus=2 -b 128 --rank 0 --local_rank 0 --master_addr localhost --config_path models/resnet50/gpus=2/mp_conf.json --distributed_backend gloo --interface tailscale0
python3 main_with_runtime.py --module models.resnet50.gpus=2 -b 128 --rank 1 --local_rank 0 --master_addr localhost --config_path models/resnet50/gpus=2/mp_conf.json --distributed_backend gloo --interface tailscale0
```
Import master_addr is address of master machine and import interface.

Set python version.

