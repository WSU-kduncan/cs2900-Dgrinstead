# CEG2900 - Lab Work
Lab work for CEG 2350 at Wright State University, Department of Computer Science and Engineering
Project 1-POP creation instruction

1. Go into virtual box
2. Git the "New" Button
3. Name the OS.(In my example I am doing POP OS
4. Create Your Memory Size
5. I did 2048
6. You want to add a virtual hard disk
7. Then hit Create
8. After you hit create you want to select VDI(VirtualBox Disk Image)
9. Click Next
10. Click Dynamically allocated
11. In this event after clicking dynamically allocated. I had to mount the disk and in this case it is DVD drive E:
12. Make the disk size whatever you want. I selected 12.00 GB
13. Then Hit Create
14. Hit Create Again. 






 Project 1-Exploring Virtualization
 
 1.It looks like the Snapshot of POP os took up 2048MB
 2. The template of the Ubuntu VM took up 2597 MB
 3. The Snapshot basically takes a picture of the VM in its current state.
 4. The Template is basically going to be a template on how to create a VM like everything is already Setup
 5. ![image](https://user-images.githubusercontent.com/59849834/133356145-3ff48cac-0544-4d33-8a46-43b897d97f0f.png)
 6. ![Ubuntu template](https://user-images.githubusercontent.com/59849834/134017329-e7044019-ce69-41c7-8098-096468bf71b3.png)
 7. ![image](https://user-images.githubusercontent.com/59849834/134017691-05a9f0d4-4de6-4dca-8134-08d73c9c87de.png)





Project 1-Networking
1. The reason why this can be done is because of NAT networking
2. NAT stands for Network Address Translation



Project 1-Networking with style 

1. The first thing you want to do is click the virtual machine you want to configure like this
2. Select network 
3. On my virtual machines you can have up to 4 different network adapters, other virtual machines may have something else.
4. Click enable network adapter 
5. On the "Attached To" section you want to select the different network type of you choice
6. In this case I selected Bridged Network Connection
7. Hit Okay to save
![Ubuntu VM ping bridged connection](https://user-images.githubusercontent.com/59849834/134014255-2c193269-fdd4-4d84-b725-8f2a36f7ddd3.jpg)
![image](https://user-images.githubusercontent.com/59849834/134096327-f6e99666-1f7f-437e-8167-8308a63577b5.png)
![ubuntu screenshot](https://user-images.githubusercontent.com/59849834/134096550-5317da18-e25c-442a-a01e-559f78537acd.png)



In this case I pinged the VM from my MAC using the VM's Ip address and it returned a Ping.





