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
ms.openlocfilehash: f5140462ae3c869d58187351d2e0ff11f7b6e179
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776693"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="5a8ac-102">ISymUnmanagedDocument::GetLanguageVendor メソッド</span><span class="sxs-lookup"><span data-stu-id="5a8ac-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="5a8ac-103">このドキュメントの言語の販売元を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a8ac-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a8ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a8ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a8ac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a8ac-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5a8ac-106">[out]言語の販売元が受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5a8ac-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a8ac-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="5a8ac-107">Return Value</span></span>  
 <span data-ttu-id="5a8ac-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="5a8ac-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a8ac-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a8ac-109">See also</span></span>

- [<span data-ttu-id="5a8ac-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a8ac-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
