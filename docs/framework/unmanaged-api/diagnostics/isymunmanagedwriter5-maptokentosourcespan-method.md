---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan メソッド
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08c219dd033b39fc07159875b184cdf70e3aa3ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937866"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="cfb81-102">ISymUnmanagedWriter5::MapTokenToSourceSpan メソッド</span><span class="sxs-lookup"><span data-stu-id="cfb81-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="cfb81-103">指定したソース ファイルで指定されたソース行に指定したメタデータ トークン span をマップします。</span><span class="sxs-lookup"><span data-stu-id="cfb81-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="cfb81-104">呼び出しの間で呼び出す必要がある[OpenMapTokensToSourceSpans メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)と[CloseMapTokensToSourceSpans メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfb81-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb81-105">構文</span><span class="sxs-lookup"><span data-stu-id="cfb81-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfb81-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfb81-106">Parameters</span></span>  
  
|<span data-ttu-id="cfb81-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfb81-107">Parameter</span></span>|<span data-ttu-id="cfb81-108">説明</span><span class="sxs-lookup"><span data-stu-id="cfb81-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="cfb81-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="cfb81-109">Return Value</span></span>  
 <span data-ttu-id="cfb81-110">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="cfb81-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfb81-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="cfb81-111">Requirements</span></span>  
 <span data-ttu-id="cfb81-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cfb81-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb81-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfb81-113">See also</span></span>

- [<span data-ttu-id="cfb81-114">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfb81-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
