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
ms.openlocfilehash: b631b16334b7e5019376fbb9a3f65d7fc2ced7dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776761"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="2a3cf-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId メソッド</span><span class="sxs-lookup"><span data-stu-id="2a3cf-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="2a3cf-103">チェックサム アルゴリズム識別子を取得またはチェックサムがない場合は、すべてゼロの GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="2a3cf-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a3cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3cf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a3cf-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2a3cf-106">[out]チェックサム アルゴリズム識別子を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2a3cf-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a3cf-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2a3cf-107">Return Value</span></span>  
 <span data-ttu-id="2a3cf-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="2a3cf-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3cf-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a3cf-109">See also</span></span>

- [<span data-ttu-id="2a3cf-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a3cf-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
