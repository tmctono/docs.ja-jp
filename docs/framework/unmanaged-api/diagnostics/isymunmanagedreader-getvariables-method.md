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
ms.openlocfilehash: 637e1aed003e211654141ab397c9c0b4724753c2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615489"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="fe4cc-102">ISymUnmanagedReader::GetVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="fe4cc-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="fe4cc-103">親と名前を指定して、ローカルでない変数を返します。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe4cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe4cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe4cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe4cc-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="fe4cc-106">から変数の親。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="fe4cc-107">[in] `pVars` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="fe4cc-108">入出力で返された変数の数を受け取る変数へのポインター `pVars` 。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="fe4cc-109">入出力変数を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe4cc-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="fe4cc-110">Return Value</span></span>  
 <span data-ttu-id="fe4cc-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe4cc-112">要件</span><span class="sxs-lookup"><span data-stu-id="fe4cc-112">Requirements</span></span>  
 <span data-ttu-id="fe4cc-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="fe4cc-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4cc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe4cc-114">See also</span></span>

- [<span data-ttu-id="fe4cc-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe4cc-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
