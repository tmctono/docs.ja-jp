---
title: XML エンティティの参照はサポートされていません
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 470e5577654ce8b6bbc2732a41c130a85ddc96e5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874988"
---
# <a name="xml-entity-references-are-not-supported"></a>XML エンティティの参照はサポートされていません

XML 1.0 仕様で定義されていないエンティティ参照 (`©` など) が、XML リテラルの値として含まれています。 XML リテラルでは、`&`、`"`、`<`、`>`、および `'` の XML エンティティ参照のみがサポートされています。  
  
 **エラー ID:** BC31180  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- サポートされていないエンティティ参照を削除します。  
  
## <a name="see-also"></a>関連項目

- [XML リテラルと XML 1.0 仕様](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [XML リテラル](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
