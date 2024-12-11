# CompareLinkedList
import java.util.*;
class SL{
    class Node{
        int data;
        Node next;
        Node(int data){
            this.data=data;
            this.next=null;
        }
    }
    Node head1=null,temp1=null;
    Node head2=null,temp2=null;
    public void insert1(int data){
        Node newnode=new Node(data);
        if(head1==null){
            head1=newnode;
            temp1=newnode;
        }
        else{
            temp1.next=newnode;
            temp1=newnode;
        }
    }
    public void insert2(int data){
        Node newnode=new Node(data);
        if(head2==null){
            head2=newnode;
            temp2=newnode;
        }
        else{
            temp2.next=newnode;
            temp2=newnode;
        }
    }
    public int Compare(){
        int c1=0,c2=0,f=0;
        Node temp1=head1;
        Node temp2=head2;
        while(temp1!=null){
            c1++;
            temp1=temp1.next;
        }
        while(temp2!=null){
            c2++;
            temp2=temp2.next;
        }
        if(c1!=c2)
        return 0;
        else{
            temp1=head1;
            temp2=head2;
            while(temp1!=null&&temp2!=null){
                if(temp1.data!=temp2.data){
                    f=1;
                    break;
                }
                temp1=temp1.next;
                temp2=temp2.next;
            }
            if(f==1)
            return 0;
            else
            return 1;
        }
    }
    public static void main(String args[]){
        Scanner s=new Scanner(System.in);
        SL X=new SL();
        int t,n,m,data;
        t=s.nextInt();
        for(int i=0;i<t;i++){
            n=s.nextInt();
            for(int j=0;j<n;j++){
                data=s.nextInt();
                X.insert1(data);
            }
            m=s.nextInt();
            for(int j=0;j<n;j++){
                data=s.nextInt();
                X.insert2(data);
            }
        }
        int res=X.Compare();
        System.out.println(res);
    }
}
