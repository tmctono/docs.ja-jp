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
ms.openlocfilehash: a75fed5e3272b783a6f8fb1a4f1c02096858b409
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777900"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="f2fbb-102">ISymUnmanagedScope::GetMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="f2fbb-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="f2fbb-103">このスコープを含むメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2fbb-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2fbb-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2fbb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2fbb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2fbb-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f2fbb-106">[out]返されたポインター [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f2fbb-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2fbb-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="f2fbb-107">Return Value</span></span>  
 <span data-ttu-id="f2fbb-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="f2fbb-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2fbb-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f2fbb-109">Requirements</span></span>  
 <span data-ttu-id="f2fbb-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f2fbb-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fbb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2fbb-111">See also</span></span>

- [<span data-ttu-id="f2fbb-112">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2fbb-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
