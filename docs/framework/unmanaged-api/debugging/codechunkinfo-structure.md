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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072663"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="94911-102">CodeChunkInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="94911-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="94911-103">メモリ内のコードの単一のチャンクを表しています。</span><span class="sxs-lookup"><span data-stu-id="94911-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94911-104">構文</span><span class="sxs-lookup"><span data-stu-id="94911-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="94911-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="94911-105">Members</span></span>  
  
|<span data-ttu-id="94911-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="94911-106">Member</span></span>|<span data-ttu-id="94911-107">説明</span><span class="sxs-lookup"><span data-stu-id="94911-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="94911-108">A`CORDB_ADDRESS`チャンクの開始アドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="94911-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="94911-109">チャンクのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="94911-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94911-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="94911-110">Remarks</span></span>  
 <span data-ttu-id="94911-111">コードの 1 つのチャンクは、関数などのコード オブジェクトの一部は、ネイティブ コードの領域です。</span><span class="sxs-lookup"><span data-stu-id="94911-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94911-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="94911-112">Requirements</span></span>  
 <span data-ttu-id="94911-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94911-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94911-114">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="94911-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="94911-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94911-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="94911-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="94911-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="94911-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="94911-117">See also</span></span>

- [<span data-ttu-id="94911-118">GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="94911-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="94911-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="94911-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="94911-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="94911-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
