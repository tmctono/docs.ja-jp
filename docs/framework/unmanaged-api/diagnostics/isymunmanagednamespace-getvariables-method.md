---
title: ISymUnmanagedNamespace::GetVariables メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: 091f497024b48589953456e1ea6daf6635738240
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615086"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="3c8be-102">ISymUnmanagedNamespace::GetVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="3c8be-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="3c8be-103">この名前空間内のグローバルスコープで定義されているすべての変数を返します。</span><span class="sxs-lookup"><span data-stu-id="3c8be-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c8be-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c8be-104">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c8be-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c8be-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="3c8be-106">から`ULONG32`配列のサイズを示す `pVars` 。</span><span class="sxs-lookup"><span data-stu-id="3c8be-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="3c8be-107">入出力`ULONG32`名前空間を格納するために必要なバッファーのサイズを受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3c8be-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="3c8be-108">入出力名前空間を格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3c8be-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c8be-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="3c8be-109">Return Value</span></span>  
 <span data-ttu-id="3c8be-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c8be-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c8be-111">要件</span><span class="sxs-lookup"><span data-stu-id="3c8be-111">Requirements</span></span>  
 <span data-ttu-id="3c8be-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="3c8be-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8be-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c8be-113">See also</span></span>

- [<span data-ttu-id="3c8be-114">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c8be-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
