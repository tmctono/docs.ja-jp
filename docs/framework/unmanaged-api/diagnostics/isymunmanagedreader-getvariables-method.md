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
ms.openlocfilehash: 4590d2734ea89bc1bc8a30db1c7ecac5effafd7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429759"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="981ed-102">ISymUnmanagedReader::GetVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="981ed-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="981ed-103">親と名前を指定して、ローカルでない変数を返します。</span><span class="sxs-lookup"><span data-stu-id="981ed-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981ed-104">構文</span><span class="sxs-lookup"><span data-stu-id="981ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="981ed-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="981ed-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="981ed-106">から変数の親。</span><span class="sxs-lookup"><span data-stu-id="981ed-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="981ed-107">[in] `pVars` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="981ed-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="981ed-108">入出力`pVars`で返された変数の数を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="981ed-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="981ed-109">入出力変数を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="981ed-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="981ed-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="981ed-110">Return Value</span></span>  
 <span data-ttu-id="981ed-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="981ed-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="981ed-112">要件</span><span class="sxs-lookup"><span data-stu-id="981ed-112">Requirements</span></span>  
 <span data-ttu-id="981ed-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="981ed-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981ed-114">参照</span><span class="sxs-lookup"><span data-stu-id="981ed-114">See also</span></span>

- [<span data-ttu-id="981ed-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="981ed-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
