---
title: フレンド アセンブリ参照 <reference> は無効です
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0966cea26c5dde8f116081c7a6411b4275e50f40
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817046"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="d545b-102">フレンド アセンブリ参照\<参照 > が無効です</span><span class="sxs-lookup"><span data-stu-id="d545b-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="d545b-103">フレンド アセンブリ参照\<参照 > が無効です。</span><span class="sxs-lookup"><span data-stu-id="d545b-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="d545b-104">厳密な名前の署名つきアセンブリはその InternalsVisibleTo 宣言内で公開キーを指定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d545b-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="d545b-105">渡すアセンブリ名、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性コンス トラクターは、厳密な名前のアセンブリを識別しますは含まれません、`PublicKey`属性。</span><span class="sxs-lookup"><span data-stu-id="d545b-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="d545b-106">**エラー ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="d545b-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d545b-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d545b-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="d545b-108">厳密な名前のフレンド アセンブリの公開キーを確認します。</span><span class="sxs-lookup"><span data-stu-id="d545b-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="d545b-109">渡されるアセンブリ名の一部として、公開キーを含めて、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性のコンス トラクターを使用して、`PublicKey`属性。</span><span class="sxs-lookup"><span data-stu-id="d545b-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d545b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d545b-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="d545b-111">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="d545b-111">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
