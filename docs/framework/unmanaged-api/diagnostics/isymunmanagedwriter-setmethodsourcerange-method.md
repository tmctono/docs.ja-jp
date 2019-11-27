---
title: ISymUnmanagedWriter::SetMethodSourceRange メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: 85e65f6a3ec13c2acc31b8f87dbe4b4476ffc2a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427871"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="16aa7-102">ISymUnmanagedWriter::SetMethodSourceRange メソッド</span><span class="sxs-lookup"><span data-stu-id="16aa7-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="16aa7-103">ソースファイル内のメソッドの実際の開始と終了を指定します。</span><span class="sxs-lookup"><span data-stu-id="16aa7-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="16aa7-104">メソッドの範囲を、メソッド内に存在するシーケンスポイントとは別に指定するには、このメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="16aa7-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16aa7-105">構文</span><span class="sxs-lookup"><span data-stu-id="16aa7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16aa7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16aa7-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="16aa7-107">から開始位置を格納しているドキュメントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="16aa7-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="16aa7-108">から開始行番号。</span><span class="sxs-lookup"><span data-stu-id="16aa7-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="16aa7-109">から開始列。</span><span class="sxs-lookup"><span data-stu-id="16aa7-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="16aa7-110">から終了位置を含むドキュメントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="16aa7-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="16aa7-111">から終了行番号。</span><span class="sxs-lookup"><span data-stu-id="16aa7-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="16aa7-112">から終了列番号。</span><span class="sxs-lookup"><span data-stu-id="16aa7-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16aa7-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="16aa7-113">Return Value</span></span>  
 <span data-ttu-id="16aa7-114">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="16aa7-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16aa7-115">要件</span><span class="sxs-lookup"><span data-stu-id="16aa7-115">Requirements</span></span>  
 <span data-ttu-id="16aa7-116">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="16aa7-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16aa7-117">参照</span><span class="sxs-lookup"><span data-stu-id="16aa7-117">See also</span></span>

- [<span data-ttu-id="16aa7-118">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16aa7-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
