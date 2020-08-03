---
title: LINQ to XML の注釈
description: LINQ to XML で注釈を使用して、任意の型の任意のオブジェクトを XML ツリー内の任意の XML コンポーネントに関連付ける方法について学習します。
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: e7da666139c10b26de37816693202d96498f52d8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165578"
---
# <a name="linq-to-xml-annotations"></a>LINQ to XML の注釈

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の注釈を使用すると、任意の型の任意のオブジェクトを XML ツリー内の任意の XML コンポーネントに関連付けることができます。

<xref:System.Xml.Linq.XElement> や <xref:System.Xml.Linq.XAttribute> などの XML コンポーネントに注釈を追加するには、<xref:System.Xml.Linq.XObject.AddAnnotation%2A> メソッドを呼び出します。 注釈は型によって取得します。

注釈は XML 情報セットの一部ではないことに注意してください。注釈はシリアル化も逆シリアル化もされません。

## <a name="methods"></a>メソッド

注釈を操作する場合は、次のメソッドを使用できます。

|メソッド|説明|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|オブジェクトを <xref:System.Xml.Linq.XObject> の注釈の一覧に追加します。|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|指定された型の最初の注釈オブジェクトを <xref:System.Xml.Linq.XObject> から取得します。|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<xref:System.Xml.Linq.XObject> について指定された型の注釈のコレクションを取得します。|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|指定された型の注釈を <xref:System.Xml.Linq.XObject> から削除します。|
