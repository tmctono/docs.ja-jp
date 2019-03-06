---
title: ISymUnmanagedDocument::GetCheckSumAlgorithmId メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 116792c6a669f31b0c69dcc0b25134af7e72f9f2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501033"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="07a6d-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId メソッド</span><span class="sxs-lookup"><span data-stu-id="07a6d-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="07a6d-103">チェックサム アルゴリズム識別子を取得またはチェックサムがない場合は、すべてゼロの GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="07a6d-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07a6d-104">構文</span><span class="sxs-lookup"><span data-stu-id="07a6d-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07a6d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07a6d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="07a6d-106">[out]チェックサム アルゴリズム識別子を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="07a6d-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07a6d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="07a6d-107">Return Value</span></span>  
 <span data-ttu-id="07a6d-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="07a6d-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a6d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="07a6d-109">See also</span></span>
- [<span data-ttu-id="07a6d-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07a6d-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
