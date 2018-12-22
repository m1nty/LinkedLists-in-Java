

**********************************************************************************TEST CLASS*****************************************************************************************


/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package LL;

/**
 *
 * @author m1nty
 */
public class LL {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
       
       
        String[] a = {"blue", "yellow", "blue", "black"};
        ItemsLinkedList list =new ItemsLinkedList(a);
        list.printList();
        //tests getsize
        System.out.println(list.getSize());
        //test replace
        System.out.println(list.replace(3,"white"));//end
        list.printList();
        System.out.println(". Its size is "+list.getSize());
        System.out.println(list.replace(-3,"red"));//invalid index so does nothing but prints false
        list.printList();
        System.out.println(list.replace(0,"orange"));//at the beginging
        list.printList();
        System.out.println(list.replace(1,"purple"));//in middle
        list.printList();
        //changing back to normal
        System.out.println(list.replace(0,"blue"));
        System.out.println(list.replace(1,"yellow"));
        list.printList();

        //test for method insert
        list.insert("blue", "red");//middle
        list.printList();
        System.out.println(". Its size is "+list.getSize());
        list.insert("d", "red");//invalid index so does nothing
        list.printList();
        list.insert("blue", "orange");//beginging so will appear after first word
        list.printList();
        list.insert("white", "neon");//end 
        list.printList();
        list.insert("blue","orange");//creating duplicates of consecutive orange
        list.printList();
        list.insert("orange","silver");//places silver after each of these oranges
        list.printList();
        //remove
        System.out.println(list.getSize());//initial size before all removals
        list.remove(0);//beginging
        list.printList();
        list.remove(13);//end
        list.printList();
        list.remove(7);//middle
        list.printList();
        list.remove(-1);//invalid index not in array below 0
        list.printList();
        list.remove(20);//invalid index to big
        list.printList();
        System.out.println(list.getSize());//Final size after all the above removals, since 3 are SUCCESFULLY removed from 15 it print 12
        //Deep copy testing
        
        
        ItemsLinkedList theCopy = list.deepCopy();
        theCopy.printList();//copy printed
        theCopy.remove(0);//first index of copy deleted
        theCopy.printList();//index deleted shown
        list.printList();//original still has
        
       
    }
    
}

**********************************************************************************MyNode Class*****************************************************************************************

public class MyNode {
    String word;
    MyNode next;
    public MyNode(String w, MyNode n){
        word = w;
        next = n;
    }

 
}
**********************************************************************************ItemsLinkedList Class*****************************************************************************************

public class ItemsLinkedList {
    private MyNode head;
    private int size;
    public ItemsLinkedList(){ 
        size=0;
        head=new MyNode(null,null);//creates dummy 
    }
    public ItemsLinkedList(String[] arrayOfItems){//constructor for array given 
        head=new MyNode(null,null);
        MyNode p=head; String w;
        for(int i=0 ; i<arrayOfItems.length ; i++){//goes through list and assigns to new nodes
            w= new String(arrayOfItems[i]);
            p.next=new MyNode(w,null);
            p=p.next;//iterates
        }
        size=arrayOfItems.length;//sets size to length of array
    }
  
    public void printList(){//method to print out contents in list
        MyNode p;
        System.out.print("The list contains [");
        for(p=head.next;p!=null;p=p.next)
            System.out.print(p.word +" ");
        System.out.print("]\n");
    }

    
    public int getSize(){return this.size;} // returns size of the list
   

    
    public boolean replace(int j, String w){
        MyNode p=head;
        if((j<size)&&(j>=0)){//checks if the size is in array index limits
            for(int i=0;i<j;i++){//goes through the array till that locaiton i specified
                p=p.next;
            }
            p.next=new MyNode(w,p.next.next);//replaces with new node with string
         
            return true;
        }
        else
            return false;//returns false if index not valid
    }




   
    public void insert(String v, String w){//goes through entire linked list and every time String v comes up, a new node created next to it
        MyNode p=head;
        while(p.next!=null){//iterates through whole list
            if(p.next.word.equals(v))
            {
                p.next.next = new MyNode(w,p.next.next);//when z is seen at the next node, the node after z is assigned a new node 
                size++;//size of list increases
                
                
            }
            p = p.next;//iterate the while loop
        }
            
        
        
     }
    public void remove(int j){
        MyNode p = head;
        if (j>=0 && j<size){//assuming position 0 is first position in list.
            for(int i =0 ; i<(j) ; i++){
                p = p.next;
                
            }
            p.next = p.next.next;
            size--;
            
        }
        else{
            System.out.println("INVALID INDEX");
        }
    }
         
        
        
    public ItemsLinkedList deepCopy(){
    ItemsLinkedList theCopy=new ItemsLinkedList();
    MyNode p;
    MyNode r=theCopy.head;
    for(p=head.next;p!=null;p=p.next){
        r.next=new MyNode(p.word,null);
        theCopy.size++;
        r=r.next;
    }
    return theCopy;
    }
}


     
  
    
    

