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
ms.openlocfilehash: d2c64d7ead2f7ce3d76b40f4fdc604506ee85561
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777881"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="0b254-102">ISymUnmanagedScope::GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="0b254-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="0b254-103">このスコープ内で使用されている名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="0b254-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b254-104">構文</span><span class="sxs-lookup"><span data-stu-id="0b254-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b254-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b254-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="0b254-106">[in] `namespaces` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="0b254-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="0b254-107">[out]ポインターを`ULONG32`名前空間の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="0b254-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="0b254-108">[out]名前空間を受け取る配列。</span><span class="sxs-lookup"><span data-stu-id="0b254-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b254-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="0b254-109">Return Value</span></span>  
 <span data-ttu-id="0b254-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0b254-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b254-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="0b254-111">Requirements</span></span>  
 <span data-ttu-id="0b254-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0b254-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b254-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b254-113">See also</span></span>

- [<span data-ttu-id="0b254-114">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0b254-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
