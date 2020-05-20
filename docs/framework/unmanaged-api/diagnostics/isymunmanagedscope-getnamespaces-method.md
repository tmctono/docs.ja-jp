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
ms.openlocfilehash: 6f11a69671864ba4627c2bb8c86e0c9beb27eeb1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611121"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="6d523-102">ISymUnmanagedScope::GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="6d523-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="6d523-103">このスコープ内で使用されている名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="6d523-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d523-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d523-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d523-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d523-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="6d523-106">[in] `namespaces` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="6d523-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="6d523-107">入出力`ULONG32`名前空間を格納するために必要なバッファーのサイズを受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6d523-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="6d523-108">入出力名前空間を受け取る配列。</span><span class="sxs-lookup"><span data-stu-id="6d523-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d523-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6d523-109">Return Value</span></span>  
 <span data-ttu-id="6d523-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d523-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d523-111">要件</span><span class="sxs-lookup"><span data-stu-id="6d523-111">Requirements</span></span>  
 <span data-ttu-id="6d523-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="6d523-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d523-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d523-113">See also</span></span>

- [<span data-ttu-id="6d523-114">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d523-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
