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
ms.openlocfilehash: bc1b65de026a674a3dff183050a5a205fd7052c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427999"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="6f211-102">ISymUnmanagedWriter::DefineParameter メソッド</span><span class="sxs-lookup"><span data-stu-id="6f211-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="6f211-103">現在のメソッドの1つのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="6f211-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="6f211-104">パラメーターの型は、メソッドのシグネチャ内のパラメーターの位置 (シーケンス) から取得されます。</span><span class="sxs-lookup"><span data-stu-id="6f211-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="6f211-105">パラメーターが特定のメソッドのメタデータで定義されている場合は、このメソッドを使用してこれらを再定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6f211-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="6f211-106">シンボルリーダーは、シンボルストアを確認する前に、パラメーターの通常のメタデータを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f211-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f211-107">構文</span><span class="sxs-lookup"><span data-stu-id="6f211-107">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6f211-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f211-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6f211-109">からパラメーター名。</span><span class="sxs-lookup"><span data-stu-id="6f211-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="6f211-110">からパラメーターの属性。</span><span class="sxs-lookup"><span data-stu-id="6f211-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="6f211-111">からパラメーターシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="6f211-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="6f211-112">からアドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="6f211-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="6f211-113">からパラメーター指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="6f211-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="6f211-114">からパラメーター指定の2番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="6f211-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="6f211-115">からパラメーター指定の3番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="6f211-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f211-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="6f211-116">Return Value</span></span>  
 <span data-ttu-id="6f211-117">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6f211-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f211-118">要件</span><span class="sxs-lookup"><span data-stu-id="6f211-118">Requirements</span></span>  
 <span data-ttu-id="6f211-119">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="6f211-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f211-120">参照</span><span class="sxs-lookup"><span data-stu-id="6f211-120">See also</span></span>

- [<span data-ttu-id="6f211-121">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f211-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
