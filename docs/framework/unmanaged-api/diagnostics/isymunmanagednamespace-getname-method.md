---
title: ISymUnmanagedNamespace::GetName メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4323423d3958fa1ca652c55f8f75749bb6e1ee79
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759386"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="4f7e0-102">ISymUnmanagedNamespace::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="4f7e0-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="4f7e0-103">この名前空間の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="4f7e0-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f7e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f7e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f7e0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f7e0-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="4f7e0-106">[in]A`ULONG32`のサイズを示す、`szName`バッファー。</span><span class="sxs-lookup"><span data-stu-id="4f7e0-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4f7e0-107">[out]ポインター、`ULONG32`文字、終端の null を含む、名前空間の名前を格納するために必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="4f7e0-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="4f7e0-108">[out]名前空間の名前を格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4f7e0-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f7e0-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4f7e0-109">Return Value</span></span>  
 <span data-ttu-id="4f7e0-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="4f7e0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f7e0-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f7e0-111">Requirements</span></span>  
 <span data-ttu-id="4f7e0-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4f7e0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f7e0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f7e0-113">See also</span></span>

- [<span data-ttu-id="4f7e0-114">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f7e0-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
