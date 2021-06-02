# 栈(Stack)

栈是一种只允许在一端进行插入或删除的线性表。

+ 栈的操作端通常被称为栈顶，另一端被称为栈底。
+ 栈的插入操作称为进栈（压栈-push）。
+ 栈删除操作称为出栈（弹栈-pop）。



## 线性栈

顺序存储的栈称为顺序栈。

### 接口

```java
//Stack_Interface.java

package Stack;

public interface Stack_Interface<T> {

    void push(T e) throws Exception;//将数据压入栈

    T pop() throws Exception;//将数据从栈顶弹出

    T peek() throws Exception;//取出栈顶元素

    boolean isEmpty();//判断栈是否为空

}
```



### 实现类

```java
//Stack.java

package Stack;

public class Stack<T> implements Stack_Interface<T>{

    T[] stack;//顺序存储栈里的元素
    int p;//指针

    public Stack(){
        stack= (T[]) new Object[100];
        p=-1;
    }

    public Stack(T[] array) throws Exception {
        stack= (T[]) new Object[100];
        p=-1;
        for (T e:array)
            push(e);
    }

    @Override
    public void push(T e) throws Exception {
        if(p<stack.length)
            stack[++p]=e;
        else {
            throw new Exception("栈的空间不足");
        }
    }

    @Override
    public T pop() throws Exception {
        if(!isEmpty())
            return stack[p--];
        else {
            throw new Exception("栈内无元素");
        }
    }

    @Override
    public T peek() throws Exception {
        if(!isEmpty())
            return stack[p];
        else {
            throw new Exception("栈内无元素");
        }
    }

    @Override
    public boolean isEmpty() {
        return p==-1;
    }
}
```



## 链式栈

链式存储的栈称为链式栈。

### 接口

```java
//Stack_Interface.java

package Stack;

public interface Stack_Interface<T> {

    void push(T e) throws Exception;//将数据压入栈

    T pop() throws Exception;//将数据从栈顶弹出

    T peek() throws Exception;//取出栈顶元素

    boolean isEmpty();//判断栈是否为空

}
```



### 实现类

```java
//Stack2.java

package Stack;

public class Stack_List<T> implements Stack_Interface<T>{

    Node top;//
    Node bottom;//

    public Stack_List(){
        top=bottom=new Node();
    }


    @Override
    public void push(T e){
        Node n=new Node(e);
        n.next=top;
        top=n;
    }

    @Override
    public T pop() throws Exception {
        if(!isEmpty()){
            T e= (T) top.e;
            top=top.next;
            return e;
        }
        else throw new Exception("栈内无元素");
    }

    @Override
    public T peek() throws Exception {
        if(!isEmpty()){
            T e= (T) top.e;
            return e;
        }
        else throw new Exception("栈内无元素");
    }

    @Override
    public boolean isEmpty() {
        return top==bottom;
    }

}
```

#### Node结点

```java
package Stack;

public class Node<T> {
    T e;
    Node next;
    Node(){}
    Node(T e){
        this.e=e;
    }
}

```



