---
title: ISymUnmanagedMethod インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448782"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="a6401-102">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6401-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="a6401-103">シンボルストア内のメソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="a6401-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="a6401-104">このインターフェイスは、型関連の属性ではなく、メソッドのシンボル関連の属性にのみアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6401-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6401-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-105">Methods</span></span>  
  
|<span data-ttu-id="a6401-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-106">Method</span></span>|<span data-ttu-id="a6401-107">説明</span><span class="sxs-lookup"><span data-stu-id="a6401-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6401-108">GetNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="a6401-109">このメソッドが定義されている名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="a6401-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="a6401-110">GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="a6401-111">ドキュメント内の指定された位置に対応する、このメソッド内のオフセットを返します。</span><span class="sxs-lookup"><span data-stu-id="a6401-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="a6401-112">GetParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="a6401-113">このメソッドのパラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6401-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="a6401-114">GetRanges メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="a6401-115">ドキュメント内の位置が指定されている場合、は、位置がこのメソッド内でカバーする Microsoft 中間言語 (MSIL) の範囲に対応する開始オフセットと終了オフセットのペアの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="a6401-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="a6401-116">GetRootScope メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="a6401-117">このメソッド内のルート構文のスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6401-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="a6401-118">このスコープはメソッド全体を囲みます。</span><span class="sxs-lookup"><span data-stu-id="a6401-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="a6401-119">GetScopeFromOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="a6401-120">指定されたオフセットを囲む、このメソッド内で最も外側にある構文のスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6401-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="a6401-121">GetSequencePointCount メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="a6401-122">このメソッド内のシーケンスポイントの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a6401-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="a6401-123">GetSequencePoints メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="a6401-124">このメソッド内のすべてのシーケンスポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6401-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="a6401-125">GetSourceStartEnd メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="a6401-126">このメソッドのソースのドキュメントの開始位置と終了位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="a6401-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="a6401-127">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="a6401-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="a6401-128">このメソッドのメタデータトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="a6401-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6401-129">要件</span><span class="sxs-lookup"><span data-stu-id="a6401-129">Requirements</span></span>  
 <span data-ttu-id="a6401-130">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a6401-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6401-131">参照</span><span class="sxs-lookup"><span data-stu-id="a6401-131">See also</span></span>

- [<span data-ttu-id="a6401-132">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6401-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
