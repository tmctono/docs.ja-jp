---
title: ISymUnmanagedMethod::GetScopeFromOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: 36b1b2394907f242c0e8c5e277c0d1c5b3b02e1b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448904"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="2a3bb-102">ISymUnmanagedMethod::GetScopeFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="2a3bb-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="2a3bb-103">指定されたオフセットを囲む、このメソッド内で最も外側にある構文のスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="2a3bb-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="2a3bb-104">これは、ローカル変数の検索を開始するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a3bb-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3bb-105">構文</span><span class="sxs-lookup"><span data-stu-id="2a3bb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3bb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a3bb-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="2a3bb-107">からオフセットを格納している `ULONG`。</span><span class="sxs-lookup"><span data-stu-id="2a3bb-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2a3bb-108">入出力返された[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)インターフェイスに設定されたポインター。</span><span class="sxs-lookup"><span data-stu-id="2a3bb-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a3bb-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2a3bb-109">Return Value</span></span>  
 <span data-ttu-id="2a3bb-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a3bb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3bb-111">要件</span><span class="sxs-lookup"><span data-stu-id="2a3bb-111">Requirements</span></span>  
 <span data-ttu-id="2a3bb-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="2a3bb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3bb-113">参照</span><span class="sxs-lookup"><span data-stu-id="2a3bb-113">See also</span></span>

- [<span data-ttu-id="2a3bb-114">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a3bb-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
