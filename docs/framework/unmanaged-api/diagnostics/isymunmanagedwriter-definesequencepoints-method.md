---
title: ISymUnmanagedWriter::DefineSequencePoints メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f07685351425a4685ac4a0c8e1b8e3c198b14187
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777302"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="bcefe-102">ISymUnmanagedWriter::DefineSequencePoints メソッド</span><span class="sxs-lookup"><span data-stu-id="bcefe-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="bcefe-103">現在のメソッド内のシーケンス ポイントのグループを定義します。</span><span class="sxs-lookup"><span data-stu-id="bcefe-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="bcefe-104">各開始行と開始列は、メソッド内のステートメントの先頭を定義します。</span><span class="sxs-lookup"><span data-stu-id="bcefe-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="bcefe-105">それぞれの終了行と列の終了は、メソッド内のステートメントの末尾を定義します。</span><span class="sxs-lookup"><span data-stu-id="bcefe-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="bcefe-106">配列は、オフセットの昇順に並べ替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcefe-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="bcefe-107">オフセットは常に (バイト単位)、メソッドの先頭から測定されます。</span><span class="sxs-lookup"><span data-stu-id="bcefe-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcefe-108">構文</span><span class="sxs-lookup"><span data-stu-id="bcefe-108">Syntax</span></span>  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcefe-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcefe-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="bcefe-110">[in]シーケンス ポイントが定義されているドキュメント オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bcefe-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="bcefe-111">[in]A`ULONG32`のそれぞれのサイズを示す、 `offsets`、 `lines`、 `columns`、 `endLines`、および`endColumns`バッファー。</span><span class="sxs-lookup"><span data-stu-id="bcefe-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="bcefe-112">[in]シーケンス ポイントのオフセットは、メソッドの先頭から計測されます。</span><span class="sxs-lookup"><span data-stu-id="bcefe-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="bcefe-113">[in]シーケンス ポイントの開始行番号。</span><span class="sxs-lookup"><span data-stu-id="bcefe-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="bcefe-114">[in]シーケンス ポイントの開始列番号。</span><span class="sxs-lookup"><span data-stu-id="bcefe-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="bcefe-115">[in]シーケンス ポイントの終了行番号。</span><span class="sxs-lookup"><span data-stu-id="bcefe-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="bcefe-116">このパラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="bcefe-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="bcefe-117">[in]シーケンス ポイントの終了列番号。</span><span class="sxs-lookup"><span data-stu-id="bcefe-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="bcefe-118">このパラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="bcefe-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcefe-119">戻り値</span><span class="sxs-lookup"><span data-stu-id="bcefe-119">Return Value</span></span>  
 <span data-ttu-id="bcefe-120">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bcefe-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcefe-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="bcefe-121">Requirements</span></span>  
 <span data-ttu-id="bcefe-122">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bcefe-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcefe-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcefe-123">See also</span></span>

- [<span data-ttu-id="bcefe-124">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcefe-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
