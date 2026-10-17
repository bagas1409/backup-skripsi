from ultralytics import YOLO

# 1. Unduh arsitektur dasar YOLO tipe klasifikasi (ukuran 'small' agar ringan namun akurat)
model = YOLO('yolov8s-cls.pt')

# 2. Mulai proses pelatihan (training)
# Parameter 'imgsz' diatur ke 224 (standar klasifikasi) untuk mempercepat proses tanpa membuang kualitas
hasil_training = model.train(
    data='/content/dataset_split',
    epochs=50,       # Sesuai target di prolog1.md
    imgsz=224,
    batch=32,
    device=0,        # Menggunakan GPU
    name='klasifikasi_kakao'
)

Ultralytics 8.4.121 🚀 Python-3.12.13 torch-2.11.0+cu128 CUDA:0 (Tesla T4, 14913MiB)
engine/trainer: agnostic_nms=False, amp=True, angle=1.0, augment=False, auto_augment=randaugment, batch=32, bgr=0.0, box=7.5, cache=False, cfg=None, channels_last=False, classes=None, close_mosaic=10, cls=0.5, cls_pw=0.0, cls_remap=True, compile=False, conf=None, copy_paste=0.0, copy_paste_mode=flip, cos_lr=False, cutmix=0.0, data=/content/dataset_split, degrees=0.0, deterministic=True, device=0, dfl=1.5, dgrad=0.5, dis=6.0, distill_model=None, dlam=1.0, dlog=1.0, dnn=False, dropout=0.0, dynamic=False, embed=None, end2end=None, epochs=50, erasing=0.4, exist_ok=False, fliplr=0.5, flipud=0.0, format=torchscript, fraction=1.0, freeze=None, hsv_h=0.015, hsv_s=0.7, hsv_v=0.4, imgsz=224, iou=0.7, keras=False, kobj=1.0, line_width=None, lr0=0.01, lrf=0.01, mask_ratio=4, max_det=300, mixup=0.0, mode=train, model=yolov8s-cls.pt, momentum=0.937, mosaic=1.0, multi_scale=0.0, name=klasifikasi_kakao-6, nbs=64, nms=False, opset=None, optimize=False, optimizer=auto, overlap_mask=True, patience=100, perspective=0.0, plots=True, pose=12.0, pretrained=True, profile=False, project=None, quantize=None, rect=False, resume=False, retina_masks=False, rle=1.0, save=True, save_conf=False, save_crop=False, save_dir=/content/yolov9/runs/classify/klasifikasi_kakao-6, save_frames=False, save_json=False, save_period=-1, save_txt=False, scale=0.5, seed=0, shear=0.0, show=False, show_boxes=True, show_conf=True, show_labels=True, simplify=True, single_cls=False, source=None, split=val, stream_buffer=False, task=classify, time=None, tracker=tracktrack.yaml, translate=0.1, val=True, verbose=True, vid_stride=1, visualize=False, warmup_bias_lr=0.1, warmup_epochs=3.0, warmup_momentum=0.8, weight_decay=0.0005, workers=8, workspace=None
train: /content/dataset_split/train... found 3511 images in 3 classes ✅ 
val: /content/dataset_split/val... found 438 images in 3 classes ✅ 
test: /content/dataset_split/test... found 441 images in 3 classes ✅ 
Overriding model.yaml nc=1000 with nc=3

                   from  n    params  module                                       arguments                     
  0                  -1  1       928  ultralytics.nn.modules.conv.Conv             [3, 32, 3, 2]                 
  1                  -1  1     18560  ultralytics.nn.modules.conv.Conv             [32, 64, 3, 2]                
  2                  -1  1     29056  ultralytics.nn.modules.block.C2f             [64, 64, 1, True]             
  3                  -1  1     73984  ultralytics.nn.modules.conv.Conv             [64, 128, 3, 2]               
  4                  -1  2    197632  ultralytics.nn.modules.block.C2f             [128, 128, 2, True]           
  5                  -1  1    295424  ultralytics.nn.modules.conv.Conv             [128, 256, 3, 2]              
  6                  -1  2    788480  ultralytics.nn.modules.block.C2f             [256, 256, 2, True]           
  7                  -1  1   1180672  ultralytics.nn.modules.conv.Conv             [256, 512, 3, 2]              
  8                  -1  1   1838080  ultralytics.nn.modules.block.C2f             [512, 512, 1, True]           
  9                  -1  1    661763  ultralytics.nn.modules.head.Classify         [512, 3]                      
YOLOv8s-cls summary: 56 layers, 5,084,579 parameters, 5,084,579 gradients, 12.6 GFLOPs
Transferred 156/158 items from pretrained weights
AMP: running Automatic Mixed Precision (AMP) checks...
Downloading https://github.com/ultralytics/assets/releases/download/v8.4.0/yolo26n.pt to 'yolo26n.pt': 100% ━━━━━━━━━━━━ 5.3MB 106.8MB/s 0.0s
AMP: checks passed ✅
train: Fast image access ✅ (ping: 0.0±0.0 ms, read: 2234.7±1563.4 MB/s, size: 182.8 KB)
train: Scanning /content/dataset_split/train... 3511 images, 0 corrupt: 100% ━━━━━━━━━━━━ 3511/3511 5.2Kit/s 0.7s
train: New cache created: /content/dataset_split/train.cache
val: Fast image access ✅ (ping: 0.0±0.0 ms, read: 1388.7±1216.1 MB/s, size: 158.2 KB)
val: Scanning /content/dataset_split/val... 438 images, 0 corrupt: 100% ━━━━━━━━━━━━ 438/438 4.3Kit/s 0.1s
val: New cache created: /content/dataset_split/val.cache
optimizer: 'optimizer=auto' found, ignoring 'lr0=0.01' and 'momentum=0.937' and determining best 'optimizer', 'lr0' and 'momentum' automatically... 
optimizer: AdamW(lr=0.001429, momentum=0.9) with parameter groups 26 weight(decay=0.0), 27 weight(decay=0.0005), 27 bias(decay=0.0)
Image sizes 224 train, 224 val
Using 2 dataloader workers
Logging results to /content/yolov9/runs/classify/klasifikasi_kakao-6
Starting training for 50 epochs...

      Epoch    GPU_mem       loss  Instances       Size
Downloading https://ultralytics.com/assets/Arial.ttf to '/root/.config/Ultralytics/Arial.ttf': 100% ━━━━━━━━━━━━ 755.1KB 21.7MB/s 0.0s
       1/50     0.695G     0.5224         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:34
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 10.6it/s 0.7s
                   all      0.936          1

      Epoch    GPU_mem       loss  Instances       Size
       2/50     0.871G     0.2042         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 26.4it/s 0.3s
                   all      0.963          1

      Epoch    GPU_mem       loss  Instances       Size
       3/50     0.875G     0.1892         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 31.3it/s 0.2s
                   all       0.92          1

      Epoch    GPU_mem       loss  Instances       Size
       4/50     0.875G      0.175         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:32
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 29.3it/s 0.2s
                   all      0.961          1

      Epoch    GPU_mem       loss  Instances       Size
       5/50     0.875G     0.1435         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:33
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.5it/s 0.2s
                   all      0.961          1

      Epoch    GPU_mem       loss  Instances       Size
       6/50     0.875G     0.1374         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:32
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 28.2it/s 0.2s
                   all      0.977          1

      Epoch    GPU_mem       loss  Instances       Size
       7/50     0.875G     0.1297         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:29
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 26.3it/s 0.3s
                   all      0.979          1

      Epoch    GPU_mem       loss  Instances       Size
       8/50     0.875G      0.129         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:30
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.0it/s 0.2s
                   all      0.982          1

      Epoch    GPU_mem       loss  Instances       Size
       9/50     0.875G     0.1096         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 21.6it/s 0.3s
                   all      0.975          1

      Epoch    GPU_mem       loss  Instances       Size
      10/50     0.875G     0.1026         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.3it/s 0.2s
                   all       0.97          1

      Epoch    GPU_mem       loss  Instances       Size
      11/50     0.875G    0.08814         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:29
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 25.6it/s 0.3s
                   all      0.968          1

      Epoch    GPU_mem       loss  Instances       Size
      12/50     0.875G     0.1009         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:31
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 26.9it/s 0.3s
                   all      0.973          1

      Epoch    GPU_mem       loss  Instances       Size
      13/50     0.875G    0.07642         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:29
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 28.5it/s 0.2s
                   all      0.963          1

      Epoch    GPU_mem       loss  Instances       Size
      14/50     0.875G    0.09029         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:29
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 28.1it/s 0.2s
                   all      0.975          1

      Epoch    GPU_mem       loss  Instances       Size
      15/50     0.875G    0.09412         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 32.6it/s 0.2s
                   all      0.982          1

      Epoch    GPU_mem       loss  Instances       Size
      16/50     0.875G    0.08225         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 24.1it/s 0.3s
                   all      0.977          1

      Epoch    GPU_mem       loss  Instances       Size
      17/50     0.875G    0.06846         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.1it/s 0.2s
                   all      0.979          1

      Epoch    GPU_mem       loss  Instances       Size
      18/50     0.875G    0.07564         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 21.4it/s 0.3s
                   all      0.973          1

      Epoch    GPU_mem       loss  Instances       Size
      19/50     0.875G    0.06896         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 31.1it/s 0.2s
                   all      0.979          1

      Epoch    GPU_mem       loss  Instances       Size
      20/50     0.875G    0.06038         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 27.4it/s 0.3s
                   all      0.984          1

      Epoch    GPU_mem       loss  Instances       Size
      21/50     0.875G    0.06598         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:29
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 25.8it/s 0.3s
                   all      0.982          1

      Epoch    GPU_mem       loss  Instances       Size
      22/50     0.875G    0.06072         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 19.7it/s 0.4s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      23/50     0.875G    0.06553         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.8it/s 0.2s
                   all      0.982          1

      Epoch    GPU_mem       loss  Instances       Size
      24/50     0.875G    0.05793         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 31.1it/s 0.2s
                   all      0.979          1

      Epoch    GPU_mem       loss  Instances       Size
      25/50     0.875G    0.05926         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:25
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 25.1it/s 0.3s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      26/50     0.875G    0.05811         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 29.4it/s 0.2s
                   all      0.984          1

      Epoch    GPU_mem       loss  Instances       Size
      27/50     0.875G    0.05179         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:25
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.3it/s 0.2s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      28/50     0.875G    0.04285         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:24
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 32.9it/s 0.2s
                   all      0.977          1

      Epoch    GPU_mem       loss  Instances       Size
      29/50     0.875G    0.03861         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 31.8it/s 0.2s
                   all      0.984          1

      Epoch    GPU_mem       loss  Instances       Size
      30/50     0.875G    0.04744         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:25
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 27.8it/s 0.3s
                   all      0.984          1

      Epoch    GPU_mem       loss  Instances       Size
      31/50     0.875G    0.04423         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 24.5it/s 0.3s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      32/50     0.875G    0.04758         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.2it/s 0.2s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      33/50     0.875G    0.04082         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.9it/s 0.2s
                   all      0.984          1

      Epoch    GPU_mem       loss  Instances       Size
      34/50     0.875G    0.04143         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 27.0it/s 0.3s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      35/50     0.875G    0.05482         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 29.9it/s 0.2s
                   all      0.986          1

      Epoch    GPU_mem       loss  Instances       Size
      36/50     0.875G     0.0524         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 23.4it/s 0.3s
                   all      0.982          1

      Epoch    GPU_mem       loss  Instances       Size
      37/50     0.875G    0.04238         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:29
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 29.7it/s 0.2s
                   all      0.982          1

      Epoch    GPU_mem       loss  Instances       Size
      38/50     0.875G    0.03798         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.2it/s 0.2s
                   all      0.984          1

      Epoch    GPU_mem       loss  Instances       Size
      39/50     0.875G    0.03264         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 30.8it/s 0.2s
                   all      0.986          1

      Epoch    GPU_mem       loss  Instances       Size
      40/50     0.875G    0.03024         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:30
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 25.6it/s 0.3s
                   all      0.986          1

      Epoch    GPU_mem       loss  Instances       Size
      41/50     0.875G    0.02735         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 18.9it/s 0.4s
                   all      0.982          1

      Epoch    GPU_mem       loss  Instances       Size
      42/50     0.875G    0.03361         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:34
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 28.8it/s 0.2s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      43/50     0.875G    0.03452         23        224: 100% ━━━━━━━━━━━━ 110/110 1.2it/s 1:29
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 24.9it/s 0.3s
                   all      0.991          1

      Epoch    GPU_mem       loss  Instances       Size
      44/50     0.875G    0.03368         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 28.1it/s 0.2s
                   all      0.991          1

      Epoch    GPU_mem       loss  Instances       Size
      45/50     0.875G    0.02925         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:27
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 28.6it/s 0.2s
                   all      0.991          1

      Epoch    GPU_mem       loss  Instances       Size
      46/50     0.875G      0.033         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:25
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 23.8it/s 0.3s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      47/50     0.875G    0.03206         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:25
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 25.4it/s 0.3s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      48/50     0.875G    0.02594         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:28
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 29.7it/s 0.2s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      49/50     0.875G    0.02762         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:25
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 37.8it/s 0.2s
                   all      0.989          1

      Epoch    GPU_mem       loss  Instances       Size
      50/50     0.875G     0.0267         23        224: 100% ━━━━━━━━━━━━ 110/110 1.3it/s 1:26
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 27.3it/s 0.3s
                   all      0.991          1

50 epochs completed in 1.237 hours.
Optimizer stripped from /content/yolov9/runs/classify/klasifikasi_kakao-6/weights/last.pt, 10.3MB
Optimizer stripped from /content/yolov9/runs/classify/klasifikasi_kakao-6/weights/best.pt, 10.3MB

Validating /content/yolov9/runs/classify/klasifikasi_kakao-6/weights/best.pt...
Ultralytics 8.4.121 🚀 Python-3.12.13 torch-2.11.0+cu128 CUDA:0 (Tesla T4, 14913MiB)
YOLOv8s-cls summary (fused): 30 layers, 5,079,043 parameters, 0 gradients, 12.4 GFLOPs
train: /content/dataset_split/train... found 3511 images in 3 classes ✅ 
val: /content/dataset_split/val... found 438 images in 3 classes ✅ 
test: /content/dataset_split/test... found 441 images in 3 classes ✅ 
               classes   top1_acc   top5_acc: 100% ━━━━━━━━━━━━ 7/7 1.5s/it 10.3s
                   all      0.991          1
Speed: 0.1ms preprocess, 0.4ms inference, 0.0ms loss, 0.0ms postprocess per image
Results saved to /content/yolov9/runs/classify/klasifikasi_kakao-6