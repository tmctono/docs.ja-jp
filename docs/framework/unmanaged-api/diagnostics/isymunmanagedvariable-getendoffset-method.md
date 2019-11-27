---
title: ISymUnmanagedVariable::GetEndOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
ms.openlocfilehash: 4ac1fc0b3567c49dfb36d2886926bee72d62a8dd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446065"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="f7d39-102">ISymUnmanagedVariable::GetEndOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="f7d39-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="f7d39-103">親内のこの変数の終了オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7d39-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="f7d39-104">スコープ内のローカル変数の場合は、スコープに対して定義されたオフセット内に終了オフセットが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7d39-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d39-105">構文</span><span class="sxs-lookup"><span data-stu-id="f7d39-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7d39-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7d39-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f7d39-107">入出力終了オフセットを受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7d39-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7d39-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f7d39-108">Return Value</span></span>  
 <span data-ttu-id="f7d39-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7d39-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d39-110">要件</span><span class="sxs-lookup"><span data-stu-id="f7d39-110">Requirements</span></span>  
 <span data-ttu-id="f7d39-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="f7d39-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d39-112">参照</span><span class="sxs-lookup"><span data-stu-id="f7d39-112">See also</span></span>

- [<span data-ttu-id="f7d39-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7d39-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="f7d39-114">GetStartOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="f7d39-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
