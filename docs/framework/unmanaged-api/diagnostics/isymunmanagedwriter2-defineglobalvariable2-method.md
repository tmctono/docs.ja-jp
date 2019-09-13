---
title: ISymUnmanagedWriter2::DefineGlobalVariable2 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a54d3cb1bb9abf740c2c9b5a9a8312a9612ae658
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894457"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="4cfb4-102">ISymUnmanagedWriter2::DefineGlobalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="4cfb4-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="4cfb4-103">1つのグローバル変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cfb4-104">構文</span><span class="sxs-lookup"><span data-stu-id="4cfb4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cfb4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cfb4-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4cfb4-106">からグローバル変数名。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="4cfb4-107">からグローバル変数属性。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="4cfb4-108">から署名のメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="4cfb4-109">からアドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="4cfb4-110">からパラメーター指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="4cfb4-111">からパラメーター指定の2番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="4cfb4-112">からパラメーター指定の3番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cfb4-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="4cfb4-113">Return Value</span></span>  
 <span data-ttu-id="4cfb4-114">メソッドが成功した場合は S_OK を返します。それ以外の場合は E_FAIL またはその他のエラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="4cfb4-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cfb4-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="4cfb4-115">Requirements</span></span>  
 <span data-ttu-id="4cfb4-116">**ヘッダー:** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="4cfb4-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfb4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cfb4-117">See also</span></span>

- [<span data-ttu-id="4cfb4-118">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cfb4-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="4cfb4-119">DefineGlobalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="4cfb4-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
