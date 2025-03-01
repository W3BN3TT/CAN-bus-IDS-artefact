Check if vcan0 exists:

ip link show vcan0

You should see output similar to:

3: vcan0: <NOARP,UP,LOWER_UP> mtu 72 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000

Bring Up vcan0 (if necessary): If vcan0 is missing or inactive:

sudo modprobe vcan
sudo ip link add dev vcan0 type vcan
sudo ip link set up vcan0

Test cangen and candump: Send random messages to the vcan0 interface and verify:

# Start listening for messages
candump vcan0

# In a separate terminal, send random messages
cangen vcan0

If candump doesn't show messages, there's a system-level issue with vcan.

the imports used in the other blocks of code must be installed on your device along with python3 and vcan
to initiate each section:
sudo python3 send14.py
python3 rec2.py
python3 ids61.py
