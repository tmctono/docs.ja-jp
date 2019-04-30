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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16e91a0c748e5b148e79dc73cf213b03c68c5021
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939725"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="9358d-102">ISymUnmanagedENCUpdate::GetLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="9358d-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="9358d-103">ローカル変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="9358d-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9358d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9358d-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9358d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9358d-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="9358d-106">[in]メソッドのメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="9358d-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="9358d-107">[in]A`ULONG`のサイズを示す、`rgLocals`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="9358d-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="9358d-108">[out]返される配列の[ISymUnmanagedVariable](isymunmanagedvariable-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="9358d-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9358d-109">[out]ポインターを`ULONG`のサイズを受け取る、`rgLocals`にローカル変数を含めることが必要なバッファー。</span><span class="sxs-lookup"><span data-stu-id="9358d-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9358d-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="9358d-110">Return Value</span></span>  
 <span data-ttu-id="9358d-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="9358d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9358d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="9358d-112">Requirements</span></span>  
 <span data-ttu-id="9358d-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9358d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9358d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9358d-114">See also</span></span>

- [<span data-ttu-id="9358d-115">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9358d-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
