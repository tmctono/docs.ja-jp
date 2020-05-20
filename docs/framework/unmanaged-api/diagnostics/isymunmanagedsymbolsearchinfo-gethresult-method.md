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
ms.openlocfilehash: 9dcd8282adf200932e86c950bee0b073780ce02d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615307"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="369d9-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT メソッド</span><span class="sxs-lookup"><span data-stu-id="369d9-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="369d9-103">HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="369d9-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="369d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="369d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="369d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="369d9-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="369d9-106">入出力HRESULT へのポインター。</span><span class="sxs-lookup"><span data-stu-id="369d9-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="369d9-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="369d9-107">Return Value</span></span>  
 <span data-ttu-id="369d9-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="369d9-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="369d9-109">要件</span><span class="sxs-lookup"><span data-stu-id="369d9-109">Requirements</span></span>  
 <span data-ttu-id="369d9-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="369d9-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369d9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="369d9-111">See also</span></span>

- [<span data-ttu-id="369d9-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="369d9-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
