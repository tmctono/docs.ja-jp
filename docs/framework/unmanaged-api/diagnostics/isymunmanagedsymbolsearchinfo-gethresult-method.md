---
title: ISymUnmanagedSymbolSearchInfo::GetHRESULT メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: 21f6cf18ee7d883e1792b597e08724946f53eda9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446193"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="6af6e-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT メソッド</span><span class="sxs-lookup"><span data-stu-id="6af6e-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="6af6e-103">HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="6af6e-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af6e-104">構文</span><span class="sxs-lookup"><span data-stu-id="6af6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6af6e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6af6e-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="6af6e-106">入出力HRESULT へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6af6e-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6af6e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="6af6e-107">Return Value</span></span>  
 <span data-ttu-id="6af6e-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6af6e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6af6e-109">要件</span><span class="sxs-lookup"><span data-stu-id="6af6e-109">Requirements</span></span>  
 <span data-ttu-id="6af6e-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="6af6e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af6e-111">参照</span><span class="sxs-lookup"><span data-stu-id="6af6e-111">See also</span></span>

- [<span data-ttu-id="6af6e-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6af6e-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
