---
title: ISymUnmanagedDocument::GetLanguageVendor メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25797822fc147c973ee06a52669aa9bf3c25422e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496249"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="57b89-102">ISymUnmanagedDocument::GetLanguageVendor メソッド</span><span class="sxs-lookup"><span data-stu-id="57b89-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="57b89-103">このドキュメントの言語の販売元を取得します。</span><span class="sxs-lookup"><span data-stu-id="57b89-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57b89-104">構文</span><span class="sxs-lookup"><span data-stu-id="57b89-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57b89-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="57b89-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="57b89-106">[out]言語の販売元が受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="57b89-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57b89-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="57b89-107">Return Value</span></span>  
 <span data-ttu-id="57b89-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="57b89-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b89-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="57b89-109">See also</span></span>
- [<span data-ttu-id="57b89-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57b89-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
