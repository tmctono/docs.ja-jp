---
title: ISymUnmanagedWriter::DefineParameter メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5b82415635980f5bd4e13e87a0a03ec5b7032bb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777328"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="4e6b4-102">ISymUnmanagedWriter::DefineParameter メソッド</span><span class="sxs-lookup"><span data-stu-id="4e6b4-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="4e6b4-103">現在のメソッドでは、1 つのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="4e6b4-104">パラメーターの型は、メソッドのシグネチャ内のパラメーターの位置 (シーケンス) から取得されます。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="4e6b4-105">パラメーターは、特定のメソッドのメタデータで定義されているが場合、このメソッドを使用して、再定義することはありません。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="4e6b4-106">シンボル リーダーは、シンボル ストアを確認する前に、パラメーターの通常のメタデータをチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e6b4-107">構文</span><span class="sxs-lookup"><span data-stu-id="4e6b4-107">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e6b4-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e6b4-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4e6b4-109">[in]パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="4e6b4-110">[in]パラメーターの属性。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="4e6b4-111">[in]パラメーター シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="4e6b4-112">[in]アドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="4e6b4-113">[in]パラメーター指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="4e6b4-114">[in]パラメーター指定の 2 番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="4e6b4-115">[in]パラメーター指定の 3 番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e6b4-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="4e6b4-116">Return Value</span></span>  
 <span data-ttu-id="4e6b4-117">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="4e6b4-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e6b4-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="4e6b4-118">Requirements</span></span>  
 <span data-ttu-id="4e6b4-119">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e6b4-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e6b4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e6b4-120">See also</span></span>

- [<span data-ttu-id="4e6b4-121">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4e6b4-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
