---
title: ISymUnmanagedMethod::GetSequencePoints メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
ms.openlocfilehash: 75d477af7395a9b7d3328b2a5787f810733f3749
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448878"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="3a486-102">ISymUnmanagedMethod::GetSequencePoints メソッド</span><span class="sxs-lookup"><span data-stu-id="3a486-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="3a486-103">このメソッド内のすべてのシーケンスポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a486-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a486-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a486-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a486-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a486-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="3a486-106">から`offsets`、`documents`、`lines`、`columns`、`endLines`、および `endColumns` の各配列のサイズを受け取る `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="3a486-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="3a486-107">入出力シーケンスポイントを格納するために必要なバッファーの長さを受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a486-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="3a486-108">からシーケンスポイントのメソッドの先頭からの MSIL (Microsoft 中間言語) オフセットを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="3a486-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="3a486-109">からシーケンスポイントが配置されているドキュメントを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="3a486-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="3a486-110">からシーケンスポイントが配置されているドキュメント内の行を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="3a486-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="3a486-111">からシーケンスポイントが配置されているドキュメント内の列を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="3a486-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="3a486-112">からシーケンスポイントが終了するドキュメント内の行の配列。</span><span class="sxs-lookup"><span data-stu-id="3a486-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="3a486-113">からシーケンスポイントが終了するドキュメント内の列の配列。</span><span class="sxs-lookup"><span data-stu-id="3a486-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a486-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a486-114">Return Value</span></span>  
 <span data-ttu-id="3a486-115">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a486-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a486-116">要件</span><span class="sxs-lookup"><span data-stu-id="3a486-116">Requirements</span></span>  
 <span data-ttu-id="3a486-117">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="3a486-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a486-118">参照</span><span class="sxs-lookup"><span data-stu-id="3a486-118">See also</span></span>

- [<span data-ttu-id="3a486-119">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a486-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
