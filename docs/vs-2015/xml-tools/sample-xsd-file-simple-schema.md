---
title: 示例 XSD 文件：简单架构 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: f7e1dde1-b4f6-4371-add4-935b68ec77d7
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dd61a665e50c04516d8c3c62489f9ccab7880b6a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58931961"
---
# <a name="sample-xsd-file-simple-schema"></a>示例 XSD 文件：简单架构
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
以下 XSD 文件用在 XSD 架构设计器文档中的各个示例中。 此文件是一个简单的订单架构。  
  
```xml  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:tns="http://tempuri.org/PurchaseOrderSchema.xsd"   
           targetNamespace="http://tempuri.org/PurchaseOrderSchema.xsd"   
           elementFormDefault="qualified">  
 <xsd:element name="PurchaseOrder" type="tns:PurchaseOrderType"/>  
 <xsd:complexType name="PurchaseOrderType">  
  <xsd:sequence>  
   <xsd:element name="ShipTo" type="tns:USAddress" maxOccurs="2"/>  
   <xsd:element name="BillTo" type="tns:USAddress"/>  
  </xsd:sequence>  
  <xsd:attribute name="OrderDate" type="xsd:date"/>  
 </xsd:complexType>  
  
 <xsd:complexType name="USAddress">  
  <xsd:sequence>  
   <xsd:element name="name"   type="xsd:string"/>  
   <xsd:element name="street" type="xsd:string"/>  
   <xsd:element name="city"   type="xsd:string"/>  
   <xsd:element name="state"  type="xsd:string"/>  
   <xsd:element name="zip"    type="xsd:integer"/>  
  </xsd:sequence>  
  <xsd:attribute name="country" type="xsd:NMTOKEN" fixed="US"/>  
 </xsd:complexType>  
</xsd:schema>  
```
