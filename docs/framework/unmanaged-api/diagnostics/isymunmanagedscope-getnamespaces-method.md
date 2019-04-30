---
title: ISymUnmanagedScope::GetNamespaces メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dc3c842bbb4b86b82d03848751673400bed193b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986116"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="a8cd3-102">ISymUnmanagedScope::GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="a8cd3-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="a8cd3-103">このスコープ内で使用されている名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8cd3-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8cd3-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8cd3-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8cd3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8cd3-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="a8cd3-106">[in] `namespaces` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="a8cd3-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="a8cd3-107">[out]ポインターを`ULONG32`名前空間の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="a8cd3-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="a8cd3-108">[out]名前空間を受け取る配列。</span><span class="sxs-lookup"><span data-stu-id="a8cd3-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8cd3-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a8cd3-109">Return Value</span></span>  
 <span data-ttu-id="a8cd3-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="a8cd3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8cd3-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8cd3-111">Requirements</span></span>  
 <span data-ttu-id="a8cd3-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a8cd3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8cd3-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8cd3-113">See also</span></span>

- [<span data-ttu-id="a8cd3-114">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8cd3-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
