---
title: ISymUnmanagedScope::GetLocals メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: bf932b63973f93c56883f099ddaadd9d1519f337
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446331"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="ddcc1-102">ISymUnmanagedScope::GetLocals メソッド</span><span class="sxs-lookup"><span data-stu-id="ddcc1-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="ddcc1-103">このスコープ内で定義されているローカル変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="ddcc1-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddcc1-104">構文</span><span class="sxs-lookup"><span data-stu-id="ddcc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddcc1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ddcc1-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="ddcc1-106">から`locals` 配列のサイズを示す `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="ddcc1-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="ddcc1-107">入出力ローカル変数を格納するために必要なバッファーのサイズを受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ddcc1-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="ddcc1-108">入出力ローカル変数を受け取る配列。</span><span class="sxs-lookup"><span data-stu-id="ddcc1-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddcc1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ddcc1-109">Return Value</span></span>  
 <span data-ttu-id="ddcc1-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddcc1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddcc1-111">要件</span><span class="sxs-lookup"><span data-stu-id="ddcc1-111">Requirements</span></span>  
 <span data-ttu-id="ddcc1-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="ddcc1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddcc1-113">参照</span><span class="sxs-lookup"><span data-stu-id="ddcc1-113">See also</span></span>

- [<span data-ttu-id="ddcc1-114">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ddcc1-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
