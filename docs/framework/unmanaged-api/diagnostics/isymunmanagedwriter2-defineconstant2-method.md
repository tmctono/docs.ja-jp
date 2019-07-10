---
title: ISymUnmanagedWriter2::DefineConstant2 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c194cea21901015153626dc5aead49ed1b2c3df7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755116"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="0f382-102">ISymUnmanagedWriter2::DefineConstant2 メソッド</span><span class="sxs-lookup"><span data-stu-id="0f382-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="0f382-103">定数値の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f382-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f382-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f382-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f382-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f382-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="0f382-106">[in]定数の名前。</span><span class="sxs-lookup"><span data-stu-id="0f382-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="0f382-107">[in]定数の値。</span><span class="sxs-lookup"><span data-stu-id="0f382-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="0f382-108">[in]定数のメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="0f382-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f382-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="0f382-109">Return Value</span></span>  
 <span data-ttu-id="0f382-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0f382-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f382-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f382-111">Requirements</span></span>  
 <span data-ttu-id="0f382-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0f382-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f382-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f382-113">See also</span></span>

- [<span data-ttu-id="0f382-114">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f382-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="0f382-115">DefineConstant メソッド</span><span class="sxs-lookup"><span data-stu-id="0f382-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
