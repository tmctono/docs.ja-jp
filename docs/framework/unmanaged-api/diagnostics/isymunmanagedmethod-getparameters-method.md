---
title: ISymUnmanagedMethod::GetParameters メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
ms.openlocfilehash: 031e9d9434bc655ba8947a2bb6aba56a150e9002
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614462"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="aef64-102">ISymUnmanagedMethod::GetParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="aef64-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="aef64-103">このメソッドのパラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aef64-103">Gets the parameters for this method.</span></span> <span data-ttu-id="aef64-104">パラメーターは、メソッドのシグネチャ内で定義されている順序で返されます。</span><span class="sxs-lookup"><span data-stu-id="aef64-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aef64-105">構文</span><span class="sxs-lookup"><span data-stu-id="aef64-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aef64-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aef64-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="aef64-107">[in] `params` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="aef64-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="aef64-108">から`ULONG32`パラメーターを格納するために必要なバッファーのサイズを受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="aef64-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="aef64-109">入出力パラメーターを受け取るバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="aef64-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aef64-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="aef64-110">Return Value</span></span>  
 <span data-ttu-id="aef64-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="aef64-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aef64-112">要件</span><span class="sxs-lookup"><span data-stu-id="aef64-112">Requirements</span></span>  
 <span data-ttu-id="aef64-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="aef64-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef64-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="aef64-114">See also</span></span>

- [<span data-ttu-id="aef64-115">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aef64-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
