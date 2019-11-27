---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 319ba58b5d012cbc0f9ddac0b83e5f3ae2ae062a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446168"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="335bf-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength メソッド</span><span class="sxs-lookup"><span data-stu-id="335bf-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="335bf-103">検索パスの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="335bf-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="335bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="335bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="335bf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="335bf-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="335bf-106">入出力検索パスの長さを格納するために必要なバッファーのサイズ (文字数) を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="335bf-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="335bf-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="335bf-107">Return Value</span></span>  
 <span data-ttu-id="335bf-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="335bf-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="335bf-109">要件</span><span class="sxs-lookup"><span data-stu-id="335bf-109">Requirements</span></span>  
 <span data-ttu-id="335bf-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="335bf-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="335bf-111">参照</span><span class="sxs-lookup"><span data-stu-id="335bf-111">See also</span></span>

- [<span data-ttu-id="335bf-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="335bf-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
