---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: cba4af737cc6a6441d38ba0f940fffe54f5c4f09
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449064"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="2db24-102">ISymUnmanagedENCUpdate::GetLocalVariableCount メソッド</span><span class="sxs-lookup"><span data-stu-id="2db24-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="2db24-103">ローカル変数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="2db24-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db24-104">構文</span><span class="sxs-lookup"><span data-stu-id="2db24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2db24-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2db24-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="2db24-106">からメソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="2db24-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="2db24-107">入出力ローカル変数の数を格納するために必要なバッファーのサイズ (文字数) を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2db24-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2db24-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2db24-108">Return Value</span></span>  
 <span data-ttu-id="2db24-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="2db24-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db24-110">要件</span><span class="sxs-lookup"><span data-stu-id="2db24-110">Requirements</span></span>  
 <span data-ttu-id="2db24-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="2db24-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db24-112">参照</span><span class="sxs-lookup"><span data-stu-id="2db24-112">See also</span></span>

- [<span data-ttu-id="2db24-113">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2db24-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
