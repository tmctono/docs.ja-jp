---
title: ICorDebugInternalFrame インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
ms.openlocfilehash: 6bc24450cdda2e3ed324256b53b2d137d1eb90e4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788483"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="ccff6-102">ICorDebugInternalFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ccff6-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="ccff6-103">スタック上のランタイム内部フレームを表します。</span><span class="sxs-lookup"><span data-stu-id="ccff6-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="ccff6-104">このインターフェイスは、テキストボックスのインターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="ccff6-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ccff6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ccff6-105">Methods</span></span>  
  
|<span data-ttu-id="ccff6-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="ccff6-106">Method</span></span>|<span data-ttu-id="ccff6-107">説明</span><span class="sxs-lookup"><span data-stu-id="ccff6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ccff6-108">GetFrameType メソッド</span><span class="sxs-lookup"><span data-stu-id="ccff6-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="ccff6-109">この内部フレームの型を取得します。</span><span class="sxs-lookup"><span data-stu-id="ccff6-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccff6-110">コメント</span><span class="sxs-lookup"><span data-stu-id="ccff6-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ccff6-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ccff6-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccff6-112">要件</span><span class="sxs-lookup"><span data-stu-id="ccff6-112">Requirements</span></span>  
 <span data-ttu-id="ccff6-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccff6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccff6-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccff6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccff6-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccff6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccff6-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccff6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccff6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccff6-117">See also</span></span>

- [<span data-ttu-id="ccff6-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ccff6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
