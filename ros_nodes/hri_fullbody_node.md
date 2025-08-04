# hri_fullbody ros node

| info.           | Description |
| --------------- | ----------- |
| stock component | Yes         |
| contains speculation | Yes   |
| Location.       | python script at /opt/pal/gallium/lib/hri_fullbody/detect    |
| related artical | !link to pages on arms and head |

## Description

!spectulation: presumably the node responsible for tracking human skeletons visible to the robot

mostly publishes to topics under the /humans/bodies/

of most interest is the /humans/bodies/[human_id]/skeleton2d
witch publishes a hri_msgs/Skeleton2D msg type describing the skeleton layout of that human

the ros msg definition is as follows:
```yaml
uint8 NOSE=0
uint8 NECK=1
uint8 RIGHT_SHOULDER=2
uint8 RIGHT_ELBOW=3
uint8 RIGHT_WRIST=4
uint8 LEFT_SHOULDER=5
uint8 LEFT_ELBOW=6
uint8 LEFT_WRIST=7
uint8 RIGHT_HIP=8
uint8 RIGHT_KNEE=9
uint8 RIGHT_ANKLE=10
uint8 LEFT_HIP=11
uint8 LEFT_KNEE=12
uint8 LEFT_ANKLE=13
uint8 LEFT_EYE=14
uint8 RIGHT_EYE=15
uint8 LEFT_EAR=16
uint8 RIGHT_EAR=17
std_msgs/Header header
  uint32 seq
  time stamp
  string frame_id
hri_msgs/NormalizedPointOfInterest2D[] skeleton
  float32 x
  float32 y
  float32 c
```

## Details

the python script that makes runs this node gets most of its funtinality form a python libarry using the import statment 
```python
from hri_fullbody.fullbody_detector import FullbodyDetector
```
this libarry can be found at /opt/pal/gallium/lib/python3/dist-packages/hri_fullbody
it use cv2 and media pipe to do the tracking 

## troubleshooting
