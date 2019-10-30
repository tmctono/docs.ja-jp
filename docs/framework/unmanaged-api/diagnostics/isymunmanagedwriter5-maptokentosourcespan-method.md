---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan メソッド
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 876804e7b825443116b1f44a02a685a73153915c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121622"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="fb468-102">ISymUnmanagedWriter5::MapTokenToSourceSpan メソッド</span><span class="sxs-lookup"><span data-stu-id="fb468-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="fb468-103">指定されたメタデータトークンを、指定されたソースファイル内の指定されたソース行スパンにマップします。</span><span class="sxs-lookup"><span data-stu-id="fb468-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="fb468-104">[Openmaptokenstosourcespans メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)と[CloseMapTokensToSourceSpans メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)の呼び出しの間で、を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb468-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb468-105">構文</span><span class="sxs-lookup"><span data-stu-id="fb468-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb468-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb468-106">Parameters</span></span>  
  
|<span data-ttu-id="fb468-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb468-107">Parameter</span></span>|<span data-ttu-id="fb468-108">説明</span><span class="sxs-lookup"><span data-stu-id="fb468-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="fb468-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="fb468-109">Return Value</span></span>  
 <span data-ttu-id="fb468-110">`HRESULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="fb468-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb468-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="fb468-111">Requirements</span></span>  
 <span data-ttu-id="fb468-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="fb468-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb468-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb468-113">See also</span></span>

- [<span data-ttu-id="fb468-114">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb468-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
