---
title: ISymUnmanagedNamespace::GetNamespaces メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e11886917964134a2530ae8484dba3cde5e7b61
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759378"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="b8076-102">ISymUnmanagedNamespace::GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="b8076-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="b8076-103">この名前空間の子を取得します。</span><span class="sxs-lookup"><span data-stu-id="b8076-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8076-104">構文</span><span class="sxs-lookup"><span data-stu-id="b8076-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8076-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8076-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="b8076-106">[in]A`ULONG32`のサイズを示す、`namespaces`配列。</span><span class="sxs-lookup"><span data-stu-id="b8076-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="b8076-107">[out]ポインターを`ULONG32`名前空間の格納に必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="b8076-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="b8076-108">[out]名前空間を格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b8076-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8076-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b8076-109">Return Value</span></span>  
 <span data-ttu-id="b8076-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b8076-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8076-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b8076-111">Requirements</span></span>  
 <span data-ttu-id="b8076-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b8076-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8076-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8076-113">See also</span></span>

- [<span data-ttu-id="b8076-114">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8076-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
