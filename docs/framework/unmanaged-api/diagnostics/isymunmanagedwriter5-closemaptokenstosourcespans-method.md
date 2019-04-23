---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans メソッド
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3dea6b9710f1ee5ccf8c51261f59b2de026f5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127778"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="fc557-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="fc557-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="fc557-103">マッピングの情報ソースへのトークンの範囲は、特別なカスタム データのセクションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fc557-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="fc557-104">閉じられた後は、以上のマッピング情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="fc557-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc557-105">構文</span><span class="sxs-lookup"><span data-stu-id="fc557-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fc557-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="fc557-106">Return Value</span></span>  
 <span data-ttu-id="fc557-107">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="fc557-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc557-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc557-108">Requirements</span></span>  
 <span data-ttu-id="fc557-109">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fc557-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc557-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc557-110">See also</span></span>

- [<span data-ttu-id="fc557-111">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc557-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
