## Categories of poor name code smells
### Mysterious Names.

```
SqlDataReader dr1;
int od; 
void button1_click();
class Page1{}
```
 
what does dr1 mean? What is od? What is Button1_Click? how's it different from button2? What is pag11?  
We have to look somewhere else to understand the meaning of that identifier   
This is symptom of code smell. 

code should be **clean** and **intention revealing** so that the reader does not have to go somewhere else to understand what is happening there.

To understand what is button1_Click doing  
we have to look at the implementation or at the form where the bottom is placed on 

#### How we can improve the code
if button is to check the availability of a product in a stock.  
if Page1 is used to view a customer.
```
SqlDataReader reader;
int overdueDays; 
void checkAvailability_click();
class ViewCustomerPage{}
```

### Meaningless Names
```
void beginCheckFunctionality_storeClientSideCheckBoxIDsArray();
```
We can't tell what does it mean  
We have to look at the implementation of this method.  
the reason is because it has more than 100 lines of code 

When our function is more than 10 lines of code means that is doing too many things 
so find a clean intention revealing name is not easy. 

When we keep our method short means that it is doing only one thing and it's easy to find a meaningful name. 

### Names with Encodings
 
```
int iMaxRequests;
var m_objCollection=new StringCollection();
``` 
 
Hungary notation was popular amongst C++ programmers. Historical reason: it was hard to tell the data type of a variable. idea by hungarian computer scientist: prefix variable names with data type
in modern IDE no need anymore: to see data type of variable just hover mouse over it and you will see. 
In second example what does object collection means? we have to look to what is stored in that collection. If this string collection is used to store the list of countries we can just call it as below

```
int maxRequests;
var countryNames=new StringCollection();
``` 
names shorter, more meaningful, more intention revealing. 
### Ambiguous Names

```
bool multiSelect(){}
``` 
 
What does this method do? We can’t tell 
if multiple items are selected or  
to select multiple items 
we have to look at the implementation of that method. symptom of code smell. 

Il nome multiSelect() non chiarisce se il metodo permette la selezione multipla di elementi o se esegue un'azione specifica quando sono stati selezionati più elementi.

#### modi per rendere il nome del metodo più chiaro:
1. Se il metodo serve per selezionare più elementi:
```
boolean enableMultiSelection() {
    // Logica per abilitare la selezione multipla
}
```
2. Se il metodo fa qualcosa quando sono selezionati più elementi:
```
boolean handleMultiSelection(){   
    // Logica per gestire la selezione multipla
}
```
3. Se il metodo verifica se la selezione multipla è abilitata:
```
boolean isMultiSelectionEnabled() {  
   // Logica per verificare se la selezione multipla è abilitata
}
```
4. Se il metodo restituisce vero o falso in base a una condizione di selezione multipla:
```
boolean hasMultipleItemsSelected() {   
   // Logica per verificare se sono selezionati più elementi
}
```


### Noisy Names
 ```
Customer theCustomer;
List<Customer> listOfApprovedCustomers;
``` 
instead we can use shorter and meaningful name:
 ```
Customer customer;
List<Customer> approvedCustomers;
```   


### **How to chose names**
- Not too short, not too long
- Meaningful
- Reveal Intention
- Chosen from problem domain  
  