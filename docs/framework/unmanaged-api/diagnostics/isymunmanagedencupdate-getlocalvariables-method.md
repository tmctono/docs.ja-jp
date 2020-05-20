---
title: ISymUnmanagedENCUpdate::GetLocalVariables メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 5e5bf097a4b1e366fff807595b22c4696a91cf43
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614553"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="79c3c-102">ISymUnmanagedENCUpdate::GetLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="79c3c-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="79c3c-103">ローカル変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c3c-104">構文</span><span class="sxs-lookup"><span data-stu-id="79c3c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79c3c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="79c3c-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="79c3c-106">からメソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="79c3c-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="79c3c-107">から`ULONG`パラメーターのサイズを示す `rgLocals` 。</span><span class="sxs-lookup"><span data-stu-id="79c3c-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="79c3c-108">入出力返される[ISymUnmanagedVariable](isymunmanagedvariable-interface.md)インスタンスの配列。</span><span class="sxs-lookup"><span data-stu-id="79c3c-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="79c3c-109">入出力`ULONG` `rgLocals` ローカルを格納するために必要なバッファーのサイズを受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="79c3c-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79c3c-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="79c3c-110">Return Value</span></span>  
 <span data-ttu-id="79c3c-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79c3c-112">要件</span><span class="sxs-lookup"><span data-stu-id="79c3c-112">Requirements</span></span>  
 <span data-ttu-id="79c3c-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="79c3c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c3c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="79c3c-114">See also</span></span>

- [<span data-ttu-id="79c3c-115">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79c3c-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
