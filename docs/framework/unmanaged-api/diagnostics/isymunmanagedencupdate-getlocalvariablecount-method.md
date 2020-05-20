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
ms.openlocfilehash: d04c9865d8272bf8d04080f6049ddfb1d4c643bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614579"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="3f577-102">ISymUnmanagedENCUpdate::GetLocalVariableCount メソッド</span><span class="sxs-lookup"><span data-stu-id="3f577-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="3f577-103">ローカル変数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="3f577-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f577-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f577-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f577-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f577-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="3f577-106">からメソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="3f577-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="3f577-107">入出力`ULONG32`ローカル変数の数を格納するために必要なバッファーのサイズ (文字数) を受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3f577-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f577-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="3f577-108">Return Value</span></span>  
 <span data-ttu-id="3f577-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f577-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f577-110">要件</span><span class="sxs-lookup"><span data-stu-id="3f577-110">Requirements</span></span>  
 <span data-ttu-id="3f577-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="3f577-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f577-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f577-112">See also</span></span>

- [<span data-ttu-id="3f577-113">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f577-113">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
