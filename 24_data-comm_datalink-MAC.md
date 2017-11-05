Please refer to textbook [chapter 11](https://github.com/cnchenpu/data-comm/blob/master/ppt/Ch11-Forouzan.ppt). <br>

# Media Access Control
- Lower layer of __Data Link Layer__, provide addressing and shared media access control.
- 1. Random Access (Contension)
- 2. Controlled Access
- 3. Channel Division

## Random Access
- No pirority, no schedule, transmission is selected __randomly__.
- No central supervisor, transmission could have __collision__.
- To solve the collision, every station have to determine:
  - when can access media?
  - what to do if media is busy?
  - transmission success or failure?
  - what to do if collision happened?
  
### ALOHA
- __Multiple Access__ - send as need
- Whenever a terminal has data, it transmits. Sender finds out whether transmission was successful or experienced a collision by listening to the broadcast from the destination station. Sender retransmits after some random time if there is a collision.
