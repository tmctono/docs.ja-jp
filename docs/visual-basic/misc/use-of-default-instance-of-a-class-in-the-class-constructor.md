---
title: クラス コンストラクター内のクラスの既定のインスタンスを使用すると、無限の再帰呼び出しを引き起こす能性があります。
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 5d239fdb7dcc5c488bf0341043b810ec7dadc083
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100322"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>クラス コンストラクター内のクラスの既定のインスタンスを使用すると、無限の再帰呼び出しを引き起こす能性があります。

クラスの既定のインスタンスは、クラス コンストラクターで使用されています。 これは、無限ループとも呼ばれる、無限の再帰呼び出しを引き起こす可能性があります。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- クラス コンストラクターから、既定のインスタンスを削除します。  
  
## <a name="see-also"></a>こちらもご覧ください

- [コンストラクター](../programming-guide/concepts/object-oriented-programming.md#constructors)
