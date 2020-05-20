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
ms.openlocfilehash: 5ec69aa06816b117fb05853001e59532629504c4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614605"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="ad698-102">ISymUnmanagedDocument::GetDocumentType メソッド</span><span class="sxs-lookup"><span data-stu-id="ad698-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="ad698-103">このドキュメントのドキュメントの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad698-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad698-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad698-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad698-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad698-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ad698-106">入出力ドキュメント型を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ad698-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad698-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ad698-107">Return Value</span></span>  
 <span data-ttu-id="ad698-108">メソッドが成功した場合は S_OK します。</span><span class="sxs-lookup"><span data-stu-id="ad698-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad698-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad698-109">See also</span></span>

- [<span data-ttu-id="ad698-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad698-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
