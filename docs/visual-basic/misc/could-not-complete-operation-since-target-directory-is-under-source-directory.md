---
title: ターゲット ディレクトリがソース ディレクトリ内にあるため、操作を完了できませんでした
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: d159b9bb3a765a2fefe99fa15dff42e979fda9e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079140"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>ターゲット ディレクトリがソース ディレクトリ内にあるため、操作を完了できませんでした

循環操作が失敗しました。 循環操作は循環しているため、完了できません。 たとえば、オブジェクト A がオブジェクト B の継承を試行し、同様にオブジェクト B がオブジェクト A の継承を試行するような場合です。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 継承を行うときには、参照の循環がないことを確認します。  
  
## <a name="see-also"></a>関連項目

- [エラーの種類](../programming-guide/language-features/error-types.md)
- [Visual Studio デバッガーでブレークポイントを使用する](/visualstudio/debugger/using-breakpoints)
