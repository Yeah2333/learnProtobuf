# Learn Protocol Buffers
## Language Guide for proto3

## Defining A Message Type
```
syntax = "proto3";

message SearchRequest {
  string query = 1;
  int32 page_number = 2;
  int32 result_per_page = 3;
}
```
*The first line is proto version
*Each has a name and a type

## Assinging Field Numbers
As you can see,each filed in the message definition has a unique number.

These filed numbers are used to identify your fields in the messsage binary format.

**NOTE** 1-15 take one byte to encode ,you should reserve 1-15 for very frequently ocurring message elements.

The smallest filed number you can specify is 1,and the largest is 536870911
.19000-19999 cant use.

## Updating A Message Type
Yous should follow these rules

* Don't change the field numbers for any existing fields.
* Default values
* Fields can be removed , then make the field number reserved
* You should follow field compatible