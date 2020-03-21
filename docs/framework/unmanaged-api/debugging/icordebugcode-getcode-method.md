---
title: ICorDebugCode::GetCode メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178999"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="87165-102">ICorDebugCode::GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="87165-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="87165-103">指定した関数のすべてのコードを取得し、逆アセンブリ用に書式設定します。</span><span class="sxs-lookup"><span data-stu-id="87165-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="87165-104">このメソッドは、.NET Framework バージョン 2.0 では非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="87165-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="87165-105">代わりに[、ICorDebugCode2::GetCode チャンクを使用します](icordebugcode2-getcodechunks-method.md)。</span><span class="sxs-lookup"><span data-stu-id="87165-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87165-106">構文</span><span class="sxs-lookup"><span data-stu-id="87165-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87165-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87165-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="87165-108">[in]関数の先頭のオフセット。</span><span class="sxs-lookup"><span data-stu-id="87165-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="87165-109">[in]関数の終了位置のオフセット。</span><span class="sxs-lookup"><span data-stu-id="87165-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="87165-110">[in]コードが`buffer`返される配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="87165-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="87165-111">[アウト]コードが返される配列。</span><span class="sxs-lookup"><span data-stu-id="87165-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="87165-112">[アウト]返されるバイト数。</span><span class="sxs-lookup"><span data-stu-id="87165-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87165-113">解説</span><span class="sxs-lookup"><span data-stu-id="87165-113">Remarks</span></span>  
 <span data-ttu-id="87165-114">関数のコードが複数のチャンクに分割されている場合、ネイティブ オフセットを増加させる順に連結されます。</span><span class="sxs-lookup"><span data-stu-id="87165-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="87165-115">命令の境界はチェックされません。</span><span class="sxs-lookup"><span data-stu-id="87165-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87165-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="87165-116">Requirements</span></span>  
 <span data-ttu-id="87165-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87165-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87165-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87165-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87165-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87165-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87165-120">**.NET フレームワークのバージョン:** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="87165-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87165-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="87165-121">See also</span></span>

- [<span data-ttu-id="87165-122">GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="87165-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
