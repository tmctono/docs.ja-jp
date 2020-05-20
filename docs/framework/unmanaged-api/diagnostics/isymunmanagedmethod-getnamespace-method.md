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
ms.openlocfilehash: cda30f3c73bf75c37ff79fc415e02382b053807e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614488"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="eb2e4-102">ISymUnmanagedMethod::GetNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="eb2e4-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="eb2e4-103">このメソッドが定義されている名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb2e4-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb2e4-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb2e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb2e4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb2e4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="eb2e4-106">入出力返された[ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)インターフェイスに設定されたポインター。</span><span class="sxs-lookup"><span data-stu-id="eb2e4-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb2e4-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="eb2e4-107">Return Value</span></span>  
 <span data-ttu-id="eb2e4-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb2e4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb2e4-109">要件</span><span class="sxs-lookup"><span data-stu-id="eb2e4-109">Requirements</span></span>  
 <span data-ttu-id="eb2e4-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="eb2e4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb2e4-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb2e4-111">See also</span></span>

- [<span data-ttu-id="eb2e4-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb2e4-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
