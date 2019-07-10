---
title: ISymUnmanagedVariable::GetStartOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dbe5b4e57f21970b518e4974707175f4bdcf02a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778221"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="0e5aa-102">ISymUnmanagedVariable::GetStartOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="0e5aa-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="0e5aa-103">この変数の親内の開始オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="0e5aa-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="0e5aa-104">スコープ内のローカル変数の場合は、開始オフセットは、スコープに対して定義されたオフセット内で分類されます。</span><span class="sxs-lookup"><span data-stu-id="0e5aa-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e5aa-105">構文</span><span class="sxs-lookup"><span data-stu-id="0e5aa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e5aa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e5aa-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0e5aa-107">[out]ポインターを`ULONG32`開始オフセットを受け取る。</span><span class="sxs-lookup"><span data-stu-id="0e5aa-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e5aa-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0e5aa-108">Return Value</span></span>  
 <span data-ttu-id="0e5aa-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0e5aa-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e5aa-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0e5aa-110">Requirements</span></span>  
 <span data-ttu-id="0e5aa-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0e5aa-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5aa-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e5aa-112">See also</span></span>

- [<span data-ttu-id="0e5aa-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e5aa-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="0e5aa-114">GetEndOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="0e5aa-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
