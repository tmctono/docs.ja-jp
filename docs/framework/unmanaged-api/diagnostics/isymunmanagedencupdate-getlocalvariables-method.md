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
ms.openlocfilehash: 48e359f8ed4d52de1cff7ca46a523f4eb80ec4c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776894"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="e99c7-102">ISymUnmanagedENCUpdate::GetLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="e99c7-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="e99c7-103">ローカル変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="e99c7-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e99c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="e99c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e99c7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e99c7-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="e99c7-106">[in]メソッドのメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="e99c7-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="e99c7-107">[in]A`ULONG`のサイズを示す、`rgLocals`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e99c7-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="e99c7-108">[out]返される配列の[ISymUnmanagedVariable](isymunmanagedvariable-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e99c7-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e99c7-109">[out]ポインターを`ULONG`のサイズを受け取る、`rgLocals`にローカル変数を含めることが必要なバッファー。</span><span class="sxs-lookup"><span data-stu-id="e99c7-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e99c7-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="e99c7-110">Return Value</span></span>  
 <span data-ttu-id="e99c7-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="e99c7-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e99c7-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="e99c7-112">Requirements</span></span>  
 <span data-ttu-id="e99c7-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e99c7-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99c7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e99c7-114">See also</span></span>

- [<span data-ttu-id="e99c7-115">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e99c7-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
