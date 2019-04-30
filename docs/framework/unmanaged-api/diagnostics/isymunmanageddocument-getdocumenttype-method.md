---
title: ISymUnmanagedDocument::GetDocumentType メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7694c9b736700466ac1299b9632440e133109288
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939894"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="b5800-102">ISymUnmanagedDocument::GetDocumentType メソッド</span><span class="sxs-lookup"><span data-stu-id="b5800-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="b5800-103">このドキュメントのドキュメントの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="b5800-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5800-104">構文</span><span class="sxs-lookup"><span data-stu-id="b5800-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5800-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5800-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b5800-106">[out]ドキュメントの種類を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b5800-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5800-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b5800-107">Return Value</span></span>  
 <span data-ttu-id="b5800-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="b5800-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5800-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5800-109">See also</span></span>

- [<span data-ttu-id="b5800-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5800-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
