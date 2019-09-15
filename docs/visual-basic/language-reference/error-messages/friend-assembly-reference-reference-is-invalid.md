---
title: フレンド アセンブリ参照 <reference> は無効です
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 6eb46c6479adc69eaf65b34c69aa69977b4d62ef
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972389"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="cb63d-102">フレンドアセンブリ参照\<の参照 > が無効です</span><span class="sxs-lookup"><span data-stu-id="cb63d-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="cb63d-103">フレンドアセンブリ参照\<の参照 > が無効です。</span><span class="sxs-lookup"><span data-stu-id="cb63d-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="cb63d-104">厳密な名前の署名つきアセンブリはその InternalsVisibleTo 宣言内で公開キーを指定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="cb63d-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="cb63d-105"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性コンストラクターに渡されたアセンブリ名は、厳密な名前を持つアセンブリを識別しますが`PublicKey` 、属性は含まれません。</span><span class="sxs-lookup"><span data-stu-id="cb63d-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="cb63d-106">**エラー ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="cb63d-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb63d-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="cb63d-107">To correct this error</span></span>  
  
1. <span data-ttu-id="cb63d-108">厳密な名前のフレンドアセンブリの公開キーを決定します。</span><span class="sxs-lookup"><span data-stu-id="cb63d-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="cb63d-109"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性`PublicKey`を使用して、属性コンストラクターに渡すアセンブリ名の一部として公開キーを含めます。</span><span class="sxs-lookup"><span data-stu-id="cb63d-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb63d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb63d-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="cb63d-111">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="cb63d-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
