---
title: ISymUnmanagedWriter::DefineGlobalVariable メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: 674089f8a1076342a2479c64e253b7dda53ade87
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615203"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="ada67-102">ISymUnmanagedWriter::DefineGlobalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="ada67-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="ada67-103">グローバル変数を 1 つ定義します。</span><span class="sxs-lookup"><span data-stu-id="ada67-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ada67-104">構文</span><span class="sxs-lookup"><span data-stu-id="ada67-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ada67-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ada67-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ada67-106">から`WCHAR`グローバル変数名を定義するへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ada67-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="ada67-107">からグローバル変数属性。</span><span class="sxs-lookup"><span data-stu-id="ada67-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="ada67-108">から`ULONG32`バッファーのサイズ (文字数) を示す `signature` 。</span><span class="sxs-lookup"><span data-stu-id="ada67-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="ada67-109">からグローバル変数シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="ada67-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="ada67-110">からアドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="ada67-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="ada67-111">からパラメーター指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="ada67-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="ada67-112">からパラメーター指定の2番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="ada67-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="ada67-113">からパラメーター指定の3番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="ada67-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ada67-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="ada67-114">Return Value</span></span>  
 <span data-ttu-id="ada67-115">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ada67-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ada67-116">要件</span><span class="sxs-lookup"><span data-stu-id="ada67-116">Requirements</span></span>  
 <span data-ttu-id="ada67-117">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="ada67-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada67-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ada67-118">See also</span></span>

- [<span data-ttu-id="ada67-119">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ada67-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ada67-120">DefineLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="ada67-120">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="ada67-121">DefineGlobalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="ada67-121">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)
