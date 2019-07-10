---
title: ISymENCUnmanagedMethod::GetDocumentsForMethodCount メソッド
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf8cca7751dd9705fd3c4371e36e836ca19be5c9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736215"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="ee53d-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount メソッド</span><span class="sxs-lookup"><span data-stu-id="ee53d-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="ee53d-103">このメソッドの行が含まれるドキュメントの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="ee53d-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee53d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ee53d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee53d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee53d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ee53d-106">[out]ポインター、`ULONG32`ドキュメントの格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="ee53d-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee53d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ee53d-107">Return Value</span></span>  
 <span data-ttu-id="ee53d-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ee53d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee53d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ee53d-109">Requirements</span></span>  
 <span data-ttu-id="ee53d-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ee53d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee53d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee53d-111">See also</span></span>

- [<span data-ttu-id="ee53d-112">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee53d-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
