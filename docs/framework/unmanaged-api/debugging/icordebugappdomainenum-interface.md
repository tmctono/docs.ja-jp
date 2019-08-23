---
title: ICorDebugAppDomainEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48c222a34e2e78f29c33e49da331d97d409bae1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949761"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="a681b-102">ICorDebugAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a681b-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="a681b-103">列挙体の次の位置から始まる指定さ`ICorDebugAppDomainEnum`れた数の値を返すメソッドを提供します。`Next`</span><span class="sxs-lookup"><span data-stu-id="a681b-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="a681b-104">このインターフェイスは、"ICorDebugEnum" のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="a681b-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a681b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a681b-105">Methods</span></span>  
  
|<span data-ttu-id="a681b-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="a681b-106">Method</span></span>|<span data-ttu-id="a681b-107">説明</span><span class="sxs-lookup"><span data-stu-id="a681b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a681b-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="a681b-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="a681b-109">現在のカーソル位置から開始して、指定した数のアプリケーションドメインをコレクションから取得します。</span><span class="sxs-lookup"><span data-stu-id="a681b-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a681b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a681b-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a681b-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a681b-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a681b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a681b-112">Requirements</span></span>  
 <span data-ttu-id="a681b-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a681b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a681b-114">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a681b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a681b-115">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="a681b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a681b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a681b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a681b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a681b-117">See also</span></span>

- [<span data-ttu-id="a681b-118">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a681b-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="a681b-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a681b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
