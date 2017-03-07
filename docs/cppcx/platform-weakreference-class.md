---
title: "Platform::WeakReference Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"  
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform::WeakReference"
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Platform::WeakReference Class
Represents a weak reference to an instance of a ref class.  
  
## Syntax  
  
```cpp 
class WeakReference  
```  
  
#### Parameters  
  
## Members  
  
### Constructors  
  
|Member|Description|  
|------------|-----------------|  
|[WeakReference::WeakReference Constructor](../cppcx/weakreference-weakreference-constructor-c-cx.md)|Initializes a new instance of the WeakReference class.|  
  
### Methods  
  
|Member|Description|  
|------------|-----------------|  
|[WeakReference::Resolve Method](../cppcx/weakreference-resolve-method-platform-namespace.md)|Returns a handle to the underlying ref class, or nullptr if the object no longer exists.|  
  
### Operators  
  
|Member|Description|  
|------------|-----------------|  
|[WeakReference::operator=](../cppcx/weakreference-operator-assign.md)|Assigns a new value to the WeakReference object.|  
  
## Remarks  
 The WeakReference class itself is not a ref class and therefore it does not inherit from Platform::Object^ and cannot be used in the signature of a public method.  

## WeakReference::operator=
Assigns a value to a WeakReference.  
  
### Syntax  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));  
  
WeakReference& operator=(const WeakReference& __otherArg);  
  
WeakReference& operator=(WeakReference&& __otherArg);  
  
WeakReference& operator=(const volatile ::Platform::Object^ const __otherArg);  
  
```  
  
### Remarks  
 The last overload in the list above enables you to assign a ref class to a WeakReference variable. In this case the ref class is downcast to [Platform::Object](../cppcx/platform-object-class.md)^. You restore the original type later by specifying it as the argument for the type parameter in the [WeakReference::Resolve\<T>](../cppcx/weakreference-resolve-method-platform-namespace.md) member function.  
  


## WeakReference::operator BoolType
Implements the safe bool pattern for the WeakReference class. Not to be called explicitly from your code.  
  
### Syntax  
  
```cpp  
BoolType BoolType()  
```  
  
## See Also  
 [Platform::WeakReference Class](../cppcx/platform-weakreference-class.md
  
## WeakReference::Resolve Method (Platform namespace)
Returns a handle to the original ref class, or `nullptr` if the object no longer exists.  
  
### Syntax  
  
```cpp  
  
template<typename T>  
T^ Resolve() const  
```  
  
### Parameters  
  
## Property Value/Return Value  
 A handle to the ref class that the WeakReference object was previously associated with, or nullptr.  
  
### Remarks  
### Example  
 This is the description for a Code Example.  
  
```  
  
Bar^ bar = ref new Bar();  
//use bar...  
  
if (bar != nullptr)  
{  
    WeakReference wr(bar);  
    Bar^ newReference = wr.Resolve<Bar>();  
}  
```  
  
 Note that the type parameter is T, not T^.  
  
## See Also  
 [Platform namespace](../cppcx/platform-namespace-c-cx.md
  
## WeakReference::WeakReference Constructor (C++/CX)
Provides various ways to construct a WeakReference.  
  
### Syntax  
  
```cpp  
WeakReference();  
WeakReference(decltype(__nullptr));  
WeakReference(const WeakReference& __otherArg);  
WeakReference(WeakReference&& __otherArg);  
explicit WeakReference(const volatile ::Platform::Object^ const __otherArg);  
```  
### Example  
  
```cpp  
  
MyClass^ mc = ref new MyClass();  
WeakReference wr(mc);  
MyClass^ copy2 = wr.Resolve<MyClass>();  
  
```  
  
### Remarks  
  
  
## See Also  
 [Platform namespace](../cppcx/platform-namespace-c-cx.md)