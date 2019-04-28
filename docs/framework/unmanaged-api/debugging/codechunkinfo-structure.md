---
title: CodeChunkInfo 構造体
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58c9d4c66af0bb9f4e66d17b18ac78ef8271bc31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609608"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="d722d-102">CodeChunkInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="d722d-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="d722d-103">メモリ内のコードの単一のチャンクを表しています。</span><span class="sxs-lookup"><span data-stu-id="d722d-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d722d-104">構文</span><span class="sxs-lookup"><span data-stu-id="d722d-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="d722d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d722d-105">Members</span></span>  
  
|<span data-ttu-id="d722d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d722d-106">Member</span></span>|<span data-ttu-id="d722d-107">説明</span><span class="sxs-lookup"><span data-stu-id="d722d-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="d722d-108">A`CORDB_ADDRESS`チャンクの開始アドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="d722d-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="d722d-109">チャンクのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="d722d-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d722d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d722d-110">Remarks</span></span>  
 <span data-ttu-id="d722d-111">コードの 1 つのチャンクは、関数などのコード オブジェクトの一部は、ネイティブ コードの領域です。</span><span class="sxs-lookup"><span data-stu-id="d722d-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d722d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d722d-112">Requirements</span></span>  
 <span data-ttu-id="d722d-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d722d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d722d-114">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="d722d-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d722d-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d722d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d722d-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d722d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d722d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d722d-117">See also</span></span>

- [<span data-ttu-id="d722d-118">GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="d722d-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="d722d-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="d722d-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d722d-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d722d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
