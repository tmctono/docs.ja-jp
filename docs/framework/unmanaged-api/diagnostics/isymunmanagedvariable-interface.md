---
title: ISymUnmanagedVariable インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610172"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="98c2b-102">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98c2b-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="98c2b-103">パラメーター、ローカル変数、フィールドなどの変数を表します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98c2b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-104">Methods</span></span>  
  
|<span data-ttu-id="98c2b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-105">Method</span></span>|<span data-ttu-id="98c2b-106">説明</span><span class="sxs-lookup"><span data-stu-id="98c2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98c2b-107">GetAddressField1 メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-107">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="98c2b-108">この変数の最初のアドレスフィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="98c2b-109">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="98c2b-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="98c2b-110">GetAddressField2 メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-110">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="98c2b-111">この変数の2番目のアドレスフィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="98c2b-112">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="98c2b-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="98c2b-113">GetAddressField3 メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-113">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="98c2b-114">この変数の3番目のアドレスフィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="98c2b-115">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="98c2b-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="98c2b-116">GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="98c2b-117">この変数のアドレスの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="98c2b-118">GetAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-118">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="98c2b-119">この変数の属性フラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="98c2b-120">GetEndOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-120">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="98c2b-121">親内のこの変数の終了オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="98c2b-122">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-122">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="98c2b-123">この変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="98c2b-124">GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-124">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="98c2b-125">この変数のシグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="98c2b-126">GetStartOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="98c2b-126">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="98c2b-127">親内のこの変数の開始オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="98c2b-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98c2b-128">要件</span><span class="sxs-lookup"><span data-stu-id="98c2b-128">Requirements</span></span>  
 <span data-ttu-id="98c2b-129">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="98c2b-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c2b-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="98c2b-130">See also</span></span>

- [<span data-ttu-id="98c2b-131">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98c2b-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
