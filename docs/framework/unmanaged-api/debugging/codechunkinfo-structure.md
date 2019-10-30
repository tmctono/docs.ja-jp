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
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132400"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="35a05-102">CodeChunkInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="35a05-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="35a05-103">メモリ内のコードの単一のチャンクを表しています。</span><span class="sxs-lookup"><span data-stu-id="35a05-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a05-104">構文</span><span class="sxs-lookup"><span data-stu-id="35a05-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="35a05-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="35a05-105">Members</span></span>  
  
|<span data-ttu-id="35a05-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="35a05-106">Member</span></span>|<span data-ttu-id="35a05-107">説明</span><span class="sxs-lookup"><span data-stu-id="35a05-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="35a05-108">チャンクの開始アドレスを指定する `CORDB_ADDRESS` 値。</span><span class="sxs-lookup"><span data-stu-id="35a05-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="35a05-109">チャンクのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="35a05-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35a05-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="35a05-110">Remarks</span></span>  
 <span data-ttu-id="35a05-111">コードの1つのチャンクは、関数などのコードオブジェクトの一部であるネイティブコードの領域です。</span><span class="sxs-lookup"><span data-stu-id="35a05-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a05-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="35a05-112">Requirements</span></span>  
 <span data-ttu-id="35a05-113">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35a05-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a05-114">**ヘッダー:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="35a05-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="35a05-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35a05-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35a05-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a05-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a05-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="35a05-117">See also</span></span>

- [<span data-ttu-id="35a05-118">GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="35a05-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="35a05-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="35a05-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="35a05-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="35a05-120">Debugging</span></span>](index.md)
