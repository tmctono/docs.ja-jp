---
title: ISymUnmanagedReader::GetGlobalVariables メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
ms.openlocfilehash: b6cf7293f1d65db1f60301f49ce655c74df3daca
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448319"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="e6e6f-102">ISymUnmanagedReader::GetGlobalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="e6e6f-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="e6e6f-103">すべてのグローバル変数を返します。</span><span class="sxs-lookup"><span data-stu-id="e6e6f-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6e6f-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6e6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6e6f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6e6f-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="e6e6f-106">から`pcVars`が指すバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="e6e6f-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="e6e6f-107">入出力変数を格納するために必要なバッファーのサイズを受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6e6f-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="e6e6f-108">入出力変数を格納しているバッファー。</span><span class="sxs-lookup"><span data-stu-id="e6e6f-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6e6f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="e6e6f-109">Return Value</span></span>  
 <span data-ttu-id="e6e6f-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e6e6f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6e6f-111">要件</span><span class="sxs-lookup"><span data-stu-id="e6e6f-111">Requirements</span></span>  
 <span data-ttu-id="e6e6f-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="e6e6f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e6f-113">参照</span><span class="sxs-lookup"><span data-stu-id="e6e6f-113">See also</span></span>

- [<span data-ttu-id="e6e6f-114">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6e6f-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
