---
title: ISymUnmanagedScope::GetParent メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d90aeb22a945f4fa1576009c700c420704dd891b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144782"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="a1a90-102">ISymUnmanagedScope::GetParent メソッド</span><span class="sxs-lookup"><span data-stu-id="a1a90-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="a1a90-103">このスコープの親スコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="a1a90-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1a90-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1a90-104">Syntax</span></span>  
  
```  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1a90-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1a90-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a1a90-106">[out]返されたポインター [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a1a90-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1a90-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1a90-107">Return Value</span></span>  
 <span data-ttu-id="a1a90-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="a1a90-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1a90-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1a90-109">Requirements</span></span>  
 <span data-ttu-id="a1a90-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a1a90-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a90-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1a90-111">See also</span></span>

- [<span data-ttu-id="a1a90-112">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1a90-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="a1a90-113">GetChildren メソッド</span><span class="sxs-lookup"><span data-stu-id="a1a90-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)
