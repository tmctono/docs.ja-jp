---
title: ISymUnmanagedWriter::OpenMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: d2d16ab0a29fadd3a64d906a64fc46c422e01c45
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610042"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="a55ea-102">ISymUnmanagedWriter::OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="a55ea-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="a55ea-103">シンボル情報を出力するメソッドを開きます。</span><span class="sxs-lookup"><span data-stu-id="a55ea-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="a55ea-104">指定されたメソッドは、シーケンスポイント、パラメーター、および構文のスコープを定義するための呼び出しの現在のメソッドになります。</span><span class="sxs-lookup"><span data-stu-id="a55ea-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="a55ea-105">メソッド全体を囲む構文の暗黙的なスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="a55ea-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="a55ea-106">以前に閉じられたメソッドを再度開くと、そのメソッドに対して定義されていたシンボルはすべて消去されます。</span><span class="sxs-lookup"><span data-stu-id="a55ea-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="a55ea-107">開いているメソッドは一度に1つしか存在できません。</span><span class="sxs-lookup"><span data-stu-id="a55ea-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a55ea-108">構文</span><span class="sxs-lookup"><span data-stu-id="a55ea-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a55ea-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a55ea-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="a55ea-110">から開くメソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="a55ea-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a55ea-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="a55ea-111">Return Value</span></span>  
 <span data-ttu-id="a55ea-112">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a55ea-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a55ea-113">要件</span><span class="sxs-lookup"><span data-stu-id="a55ea-113">Requirements</span></span>  
 <span data-ttu-id="a55ea-114">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a55ea-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55ea-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a55ea-115">See also</span></span>

- [<span data-ttu-id="a55ea-116">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a55ea-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a55ea-117">CloseMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="a55ea-117">CloseMethod Method</span></span>](isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="a55ea-118">OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="a55ea-118">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)
