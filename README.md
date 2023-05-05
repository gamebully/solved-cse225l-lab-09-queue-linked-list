Download Link: https://assignmentchef.com/product/solved-cse225l-lab-09-queue-linked-list
<br>
In today’s lab we will design and implement the Queue ADT using linked list.

<table width="0">

 <tbody>

  <tr>

   <td width="295"><strong><u>quetype.h</u></strong><strong> </strong>#ifndef QUETYPE_H_INCLUDED #define QUETYPE_H_INCLUDED class FullQueue{};class EmptyQueue{};template &lt;class ItemType&gt; class QueType{struct NodeType{ItemType info;NodeType* next;};     public:         QueType();~QueType();         void MakeEmpty();         void Enqueue(ItemType);         void Dequeue(ItemType&amp;);         bool IsEmpty();         bool IsFull();     private:NodeType *front, *rear;}; #endif // QUETYPE_H_INCLUDED <strong><u>quetype.cpp</u> </strong><strong> </strong>#include “quetype.h”#include &lt;iostream&gt; using namespace std;template &lt;class ItemType&gt; QueType&lt;ItemType&gt;::QueType(){front = NULL;     rear = NULL;}template &lt;class ItemType&gt;bool QueType&lt;ItemType&gt;::IsEmpty(){return (front == NULL);}template&lt;class ItemType&gt;bool QueType&lt;ItemType&gt;::IsFull(){NodeType* location;     try     {location = new NodeType;         delete location;         return false;}catch(bad_alloc&amp; exception){return true;}}</td>

   <td width="417">template &lt;class ItemType&gt;void QueType&lt;ItemType&gt;::Enqueue(ItemType newItem){if (IsFull())         throw FullQueue();     else{NodeType* newNode;         newNode = new NodeType;         newNode-&gt;info = newItem;         newNode-&gt;next = NULL;         if (rear == NULL)             front = newNode;         elserear-&gt;next = newNode;         rear = newNode;} }template &lt;class ItemType&gt;void QueType&lt;ItemType&gt;::Dequeue(ItemType&amp; item){if (IsEmpty())         throw EmptyQueue();     else{NodeType* tempPtr;         tempPtr = front;         item = front-&gt;info;         front = front-&gt;next;         if (front == NULL)             rear = NULL;         delete tempPtr;} }template &lt;class ItemType&gt;void QueType&lt;ItemType&gt;::MakeEmpty(){NodeType* tempPtr;     while (front != NULL){tempPtr = front;         front = front-&gt;next;         delete tempPtr;}rear = NULL;} template &lt;class ItemType&gt;QueType&lt;ItemType&gt;::~QueType(){MakeEmpty();}</td>

  </tr>

 </tbody>

</table>




Generate the <strong>Driver file (main.cpp) </strong>and check your program with the following outputs:

<table width="0">

 <tbody>

  <tr>

   <td width="405"><strong>Operation to Be Tested and Description of Action </strong></td>

   <td width="150"><strong>Input Values </strong></td>

   <td width="148"><strong>Expected Output </strong></td>

  </tr>

  <tr>

   <td width="405">•     Given a set of coin values and an amount of money, determine the minimum number of coins to make the given amount of money. The input starts with an integer <strong>n,</strong> specifying the number of coin types. Next <strong>n</strong> integers are the coin values. The final integer is the amount of money you have to make. You can assume that the amount will always be possible to make using the given coin types.</td>

   <td width="150">3   2   3   5   113   5   20   30   40</td>

   <td width="148">32</td>

  </tr>

  <tr>

   <td width="405">• Try the input 3   2   3   5   200. Explain your program’s outcome with this input.</td>

   <td width="150"> </td>

   <td width="148"> </td>

  </tr>

 </tbody>

</table>


