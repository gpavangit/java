# java
easy to learn
class queue:
    def __init__(self):
        self.queue_ds=[]
        self.front=-1
        self.rear=-1
    def enqueue(self,val):
        self.queue_ds.append(val)
        if self.front==-1:
            self.front+=1
            self.rear+=1
            print(val,"is successfully inserted")
        else:
            self.rear+=1
            print(val,"is successfully inserted")
    def dequeue(self):
        if len(self.queue_ds)==0:
            print("queue is empty")
            return
        else:
            temp=self.queue_ds.pop(self.front)
            print("delete item=",temp)
            self.rear-=1
            if len(self.queue_ds)==0:
                self.front=-1
                self.rear=-1
            return
    def display(self):
        if len(self.queue_ds)==0:
            print("queue empty")
            return
        print("the contents of queue are")
        if self.front==self.rear:
            print(self.queue_ds[self.front],"<==front<==rear")
            return
        print(self.queue_ds[self.front],"==FRONT")
        i=self.front+1
        while i<self.rear:
            print(self.queue_ds[i])
            i+=1
        print(self.queue_ds[self.rear],"<==REAR")
a=queue()
while True:
    print("***********************")
    option=int(input("enter your choice\n 1:insert\n 2:delete\n 3:display\n 4:exit\n"))
    if option==1:
        value=int(input("enter the value you want to add::"))
        a.enqueue(value)
        continue
    elif option==2:
        a.dequeue()
        continue
    elif option==3:
        a.display()
        continue
    elif option==4:
        print("exiting")
        break
    else:
        print("wrong option")
