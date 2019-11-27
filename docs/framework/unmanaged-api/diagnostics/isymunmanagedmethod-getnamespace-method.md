---
title: ISymUnmanagedMethod::GetNamespace メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: b8bbedb4c60a2df6070373f2b6a104fff094869a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448970"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="ba1bc-102">ISymUnmanagedMethod::GetNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="ba1bc-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="ba1bc-103">このメソッドが定義されている名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="ba1bc-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba1bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="ba1bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba1bc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ba1bc-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ba1bc-106">入出力返された[ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)インターフェイスに設定されたポインター。</span><span class="sxs-lookup"><span data-stu-id="ba1bc-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba1bc-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ba1bc-107">Return Value</span></span>  
 <span data-ttu-id="ba1bc-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba1bc-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba1bc-109">要件</span><span class="sxs-lookup"><span data-stu-id="ba1bc-109">Requirements</span></span>  
 <span data-ttu-id="ba1bc-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="ba1bc-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba1bc-111">参照</span><span class="sxs-lookup"><span data-stu-id="ba1bc-111">See also</span></span>

- [<span data-ttu-id="ba1bc-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ba1bc-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
