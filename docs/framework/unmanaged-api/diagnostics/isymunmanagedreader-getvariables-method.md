---
title: ISymUnmanagedReader::GetVariables メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 846ff76fb1073394cc27597c9a2015148581cc70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670002"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="f7e6d-102">ISymUnmanagedReader::GetVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="f7e6d-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="f7e6d-103">親と名前を指定、非ローカル変数を返します。</span><span class="sxs-lookup"><span data-stu-id="f7e6d-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e6d-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7e6d-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7e6d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7e6d-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="f7e6d-106">[in]変数の親です。</span><span class="sxs-lookup"><span data-stu-id="f7e6d-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="f7e6d-107">[in] `pVars` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="f7e6d-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="f7e6d-108">[out]返された変数の数を受け取る変数へのポインター`pVars`します。</span><span class="sxs-lookup"><span data-stu-id="f7e6d-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="f7e6d-109">[out]変数を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7e6d-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7e6d-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f7e6d-110">Return Value</span></span>  
 <span data-ttu-id="f7e6d-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="f7e6d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7e6d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7e6d-112">Requirements</span></span>  
 <span data-ttu-id="f7e6d-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7e6d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e6d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7e6d-114">See also</span></span>

- [<span data-ttu-id="f7e6d-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7e6d-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
