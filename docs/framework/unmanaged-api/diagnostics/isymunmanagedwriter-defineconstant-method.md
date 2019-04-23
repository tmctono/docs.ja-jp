---
title: ISymUnmanagedWriter::DefineConstant メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f470dbe4ef2ef0d5f2204ccbdd5fb64730f9a2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159758"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="216de-102">ISymUnmanagedWriter::DefineConstant メソッド</span><span class="sxs-lookup"><span data-stu-id="216de-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="216de-103">定数値の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="216de-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="216de-104">構文</span><span class="sxs-lookup"><span data-stu-id="216de-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="216de-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="216de-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="216de-106">[in]ポインターを`WCHAR`定数名を定義します。</span><span class="sxs-lookup"><span data-stu-id="216de-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="216de-107">[in]定数の値。</span><span class="sxs-lookup"><span data-stu-id="216de-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="216de-108">[in] `signature` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="216de-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="216de-109">[in]定数の型シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="216de-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="216de-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="216de-110">Return Value</span></span>  
 <span data-ttu-id="216de-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="216de-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="216de-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="216de-112">Requirements</span></span>  
 <span data-ttu-id="216de-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="216de-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216de-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="216de-114">See also</span></span>

- [<span data-ttu-id="216de-115">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="216de-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="216de-116">DefineConstant2 メソッド</span><span class="sxs-lookup"><span data-stu-id="216de-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
