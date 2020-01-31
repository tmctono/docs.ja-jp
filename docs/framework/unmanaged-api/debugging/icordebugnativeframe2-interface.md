---
title: ICorDebugNativeFrame2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: 22a3f39bc1f9b4e6cad1db4fd0a6480b7c04e8fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792751"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="b4e16-102">ICorDebugNativeFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4e16-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="b4e16-103">子と親のフレームの関係をテストするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b4e16-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4e16-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b4e16-104">Methods</span></span>  
  
|<span data-ttu-id="b4e16-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b4e16-105">Method</span></span>|<span data-ttu-id="b4e16-106">説明</span><span class="sxs-lookup"><span data-stu-id="b4e16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4e16-107">IsChild メソッド</span><span class="sxs-lookup"><span data-stu-id="b4e16-107">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="b4e16-108">現在のフレームが子フレームであるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b4e16-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="b4e16-109">IsMatchingParentFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="b4e16-109">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="b4e16-110">指定したフレームが現在のフレームの親であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b4e16-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="b4e16-111">GetStackParameterSize メソッド</span><span class="sxs-lookup"><span data-stu-id="b4e16-111">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="b4e16-112">X86 オペレーティングシステムのスタックのパラメーターの累積サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="b4e16-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4e16-113">コメント</span><span class="sxs-lookup"><span data-stu-id="b4e16-113">Remarks</span></span>  
 <span data-ttu-id="b4e16-114">このインターフェイスは、"" の "テキスト" インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="b4e16-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4e16-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b4e16-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4e16-116">要件</span><span class="sxs-lookup"><span data-stu-id="b4e16-116">Requirements</span></span>  
 <span data-ttu-id="b4e16-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4e16-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4e16-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4e16-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4e16-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4e16-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4e16-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4e16-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e16-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4e16-121">See also</span></span>

- [<span data-ttu-id="b4e16-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4e16-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b4e16-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b4e16-123">Debugging</span></span>](index.md)
