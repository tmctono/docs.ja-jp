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
ms.openlocfilehash: 3e9bff5be747c4872554a69dd316de8ca9eb9934
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650662"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="b91da-102">ISymUnmanagedWriter2::DefineConstant2 メソッド</span><span class="sxs-lookup"><span data-stu-id="b91da-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="b91da-103">定数値の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="b91da-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b91da-104">構文</span><span class="sxs-lookup"><span data-stu-id="b91da-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b91da-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b91da-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b91da-106">[in]定数の名前。</span><span class="sxs-lookup"><span data-stu-id="b91da-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="b91da-107">[in]定数の値。</span><span class="sxs-lookup"><span data-stu-id="b91da-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="b91da-108">[in]定数のメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="b91da-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b91da-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b91da-109">Return Value</span></span>  
 <span data-ttu-id="b91da-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b91da-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b91da-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b91da-111">Requirements</span></span>  
 <span data-ttu-id="b91da-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b91da-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91da-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b91da-113">See also</span></span>

- [<span data-ttu-id="b91da-114">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b91da-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="b91da-115">DefineConstant メソッド</span><span class="sxs-lookup"><span data-stu-id="b91da-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
