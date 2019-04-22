---
title: ISymUnmanagedDocument::HasEmbeddedSource メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d6c79be95ff80c8de9b07cb33be46a5f5db22b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094269"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="53a00-102">ISymUnmanagedDocument::HasEmbeddedSource メソッド</span><span class="sxs-lookup"><span data-stu-id="53a00-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="53a00-103">返します`true`ドキュメントが、デバッグのシンボルに埋め込まれたソースを返しますそれ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="53a00-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a00-104">構文</span><span class="sxs-lookup"><span data-stu-id="53a00-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53a00-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53a00-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="53a00-106">[out]デバッグのシンボルにドキュメントがソースになっているかどうかを示す変数へのポインターが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="53a00-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53a00-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="53a00-107">Return Value</span></span>  
 <span data-ttu-id="53a00-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="53a00-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a00-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="53a00-109">See also</span></span>

- [<span data-ttu-id="53a00-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53a00-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
