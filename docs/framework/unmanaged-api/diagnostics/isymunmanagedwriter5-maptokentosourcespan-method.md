---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan メソッド
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08c219dd033b39fc07159875b184cdf70e3aa3ed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181520"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="bfdcd-102">ISymUnmanagedWriter5::MapTokenToSourceSpan メソッド</span><span class="sxs-lookup"><span data-stu-id="bfdcd-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="bfdcd-103">指定したソース ファイルで指定されたソース行に指定したメタデータ トークン span をマップします。</span><span class="sxs-lookup"><span data-stu-id="bfdcd-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="bfdcd-104">呼び出しの間で呼び出す必要がある[OpenMapTokensToSourceSpans メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)と[CloseMapTokensToSourceSpans メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="bfdcd-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfdcd-105">構文</span><span class="sxs-lookup"><span data-stu-id="bfdcd-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfdcd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfdcd-106">Parameters</span></span>  
  
|<span data-ttu-id="bfdcd-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfdcd-107">Parameter</span></span>|<span data-ttu-id="bfdcd-108">説明</span><span class="sxs-lookup"><span data-stu-id="bfdcd-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="bfdcd-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bfdcd-109">Return Value</span></span>  
 <span data-ttu-id="bfdcd-110">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="bfdcd-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfdcd-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="bfdcd-111">Requirements</span></span>  
 <span data-ttu-id="bfdcd-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bfdcd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdcd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfdcd-113">See also</span></span>

- [<span data-ttu-id="bfdcd-114">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfdcd-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
