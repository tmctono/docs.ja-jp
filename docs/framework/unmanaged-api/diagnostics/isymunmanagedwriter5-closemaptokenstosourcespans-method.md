---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans メソッド
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 053727604c795bf43a9b1658d5841fe85f53090a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614631"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="7783e-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="7783e-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="7783e-103">トークンとソースの間のマッピング情報については、特別なカスタムデータセクションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7783e-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="7783e-104">閉じた後は、マッピング情報を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="7783e-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7783e-105">構文</span><span class="sxs-lookup"><span data-stu-id="7783e-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7783e-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="7783e-106">Return Value</span></span>  
 <span data-ttu-id="7783e-107">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="7783e-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7783e-108">要件</span><span class="sxs-lookup"><span data-stu-id="7783e-108">Requirements</span></span>  
 <span data-ttu-id="7783e-109">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="7783e-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7783e-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7783e-110">See also</span></span>

- [<span data-ttu-id="7783e-111">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7783e-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
