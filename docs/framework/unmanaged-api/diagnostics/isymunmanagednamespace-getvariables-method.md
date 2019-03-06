---
title: ISymUnmanagedNamespace::GetVariables メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02fd9fd3a580946cda09f0c129f02cd1218a0c9a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471434"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="1372b-102">ISymUnmanagedNamespace::GetVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="1372b-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="1372b-103">この名前空間内のグローバル スコープで定義されたすべての変数を返します。</span><span class="sxs-lookup"><span data-stu-id="1372b-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1372b-104">構文</span><span class="sxs-lookup"><span data-stu-id="1372b-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1372b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1372b-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="1372b-106">[in]A`ULONG32`のサイズを示す、`pVars`配列。</span><span class="sxs-lookup"><span data-stu-id="1372b-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="1372b-107">[out]ポインターを`ULONG32`名前空間の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="1372b-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="1372b-108">[out]名前空間を格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1372b-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1372b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="1372b-109">Return Value</span></span>  
 <span data-ttu-id="1372b-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1372b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1372b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1372b-111">Requirements</span></span>  
 <span data-ttu-id="1372b-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1372b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1372b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1372b-113">See also</span></span>
- [<span data-ttu-id="1372b-114">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1372b-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
