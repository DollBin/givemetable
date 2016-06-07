# GiveMeTable

I don't write any code yet,but it likes datatables 

---

## Usage

```javascript
var table = givemetable({
   pageIndex:1,
   pageRow:10,
   ajax:{
     url:"your data cgi",
     type:"post",
     success:function(res){
        return res;
     }
   },
   columns:[
     {name:"ID",data:"Id",sort:true},
     {name:"Name",data:"Name",sort:true},
     {
        name:"Gender",
        data:function(row,type){
            if(type == "display"){
               return ["Male","Female"][row.gender];
            }else{
               return row.gender;
            }
        },
        sort:true
     }
   ]
});

table.renderTo("#datatable");

```

## Request parameters

```
pageIndex=1
pageRow=10
columns...
```

## Server response structure

```javascript
{
  draw:1,
  data:[],
  totalNum:10
}
```

## Methods

### renderTo(HTMLElement container)

    where you want to display the table

### disable()

    when table is disabled,all of buttons and links in the table is not avaliable.

### enable()

    all of buttons and links in the table is avaliable.

### reload()

    to load data again

### on(String evt,Function handler)

    bind event listener

### destroy()

    remove the table from htmls
    
    
## Events

### init

    It is triggered when call renderTo method

### sort

    It is triggered when sort the data

### destroy

    It is triggered when table is destroyed
    
## End

    Thanks for your reading.Hope you have a good time.
