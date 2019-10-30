---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans メソッド
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 004e1ddae8a6c0262846422a2eeb4314a4c82f65
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121608"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="a9594-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="a9594-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="a9594-103">特別なカスタムデータセクションを開き、トークンからソースまでの範囲マッピング情報をに出力します。</span><span class="sxs-lookup"><span data-stu-id="a9594-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="a9594-104">メソッドが既に開いている場合や、その逆の場合にこのセクションを開くと、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="a9594-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9594-105">構文</span><span class="sxs-lookup"><span data-stu-id="a9594-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a9594-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="a9594-106">Return Value</span></span>  
 <span data-ttu-id="a9594-107">`HRESULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="a9594-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9594-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="a9594-108">Requirements</span></span>  
 <span data-ttu-id="a9594-109">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a9594-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9594-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9594-110">See also</span></span>

- [<span data-ttu-id="a9594-111">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9594-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
