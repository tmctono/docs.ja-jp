---
title: ISymUnmanagedScope::GetMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 954b1d91f33fe9a7e4df1ef51ee3666047836a17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986129"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="9535e-102">ISymUnmanagedScope::GetMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="9535e-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="9535e-103">このスコープを含むメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="9535e-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9535e-104">構文</span><span class="sxs-lookup"><span data-stu-id="9535e-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9535e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9535e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9535e-106">[out]返されたポインター [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9535e-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9535e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="9535e-107">Return Value</span></span>  
 <span data-ttu-id="9535e-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="9535e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9535e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9535e-109">Requirements</span></span>  
 <span data-ttu-id="9535e-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9535e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9535e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9535e-111">See also</span></span>

- [<span data-ttu-id="9535e-112">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9535e-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
