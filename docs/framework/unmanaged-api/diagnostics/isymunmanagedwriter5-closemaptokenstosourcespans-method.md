---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans メソッド
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3dea6b9710f1ee5ccf8c51261f59b2de026f5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962280"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="efc8a-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="efc8a-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="efc8a-103">マッピングの情報ソースへのトークンの範囲は、特別なカスタム データのセクションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="efc8a-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="efc8a-104">閉じられた後は、以上のマッピング情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="efc8a-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc8a-105">構文</span><span class="sxs-lookup"><span data-stu-id="efc8a-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="efc8a-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="efc8a-106">Return Value</span></span>  
 <span data-ttu-id="efc8a-107">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="efc8a-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efc8a-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="efc8a-108">Requirements</span></span>  
 <span data-ttu-id="efc8a-109">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="efc8a-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc8a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="efc8a-110">See also</span></span>

- [<span data-ttu-id="efc8a-111">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efc8a-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
