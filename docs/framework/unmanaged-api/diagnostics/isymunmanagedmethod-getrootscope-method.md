---
title: ISymUnmanagedMethod::GetRootScope メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: c956f5d68c992f1b08988e59038e8667b391f734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448914"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="10f40-102">ISymUnmanagedMethod::GetRootScope メソッド</span><span class="sxs-lookup"><span data-stu-id="10f40-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="10f40-103">このメソッド内のルート構文のスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="10f40-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="10f40-104">このスコープはメソッド全体を囲みます。</span><span class="sxs-lookup"><span data-stu-id="10f40-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10f40-105">構文</span><span class="sxs-lookup"><span data-stu-id="10f40-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10f40-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10f40-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="10f40-107">入出力返された[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)インターフェイスに設定されたポインター。</span><span class="sxs-lookup"><span data-stu-id="10f40-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10f40-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="10f40-108">Return Value</span></span>  
 <span data-ttu-id="10f40-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="10f40-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10f40-110">要件</span><span class="sxs-lookup"><span data-stu-id="10f40-110">Requirements</span></span>  
 <span data-ttu-id="10f40-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="10f40-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10f40-112">参照</span><span class="sxs-lookup"><span data-stu-id="10f40-112">See also</span></span>

- [<span data-ttu-id="10f40-113">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10f40-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
