---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans メソッド
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 82b46ea315009b65254735d44e355154b83b22e2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609496"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="4096b-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="4096b-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="4096b-103">特別なカスタムデータセクションを開き、トークンからソースまでの範囲マッピング情報をに出力します。</span><span class="sxs-lookup"><span data-stu-id="4096b-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="4096b-104">メソッドが既に開いている場合や、その逆の場合にこのセクションを開くと、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="4096b-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4096b-105">構文</span><span class="sxs-lookup"><span data-stu-id="4096b-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4096b-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="4096b-106">Return Value</span></span>  
 <span data-ttu-id="4096b-107">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="4096b-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4096b-108">要件</span><span class="sxs-lookup"><span data-stu-id="4096b-108">Requirements</span></span>  
 <span data-ttu-id="4096b-109">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="4096b-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4096b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4096b-110">See also</span></span>

- [<span data-ttu-id="4096b-111">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4096b-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
