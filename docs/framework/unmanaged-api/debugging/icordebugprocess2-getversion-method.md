---
title: ICorDebugProcess2::GetVersion メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
ms.openlocfilehash: 391b848d3b3f66f6af6bf3adbefb6e94d526e748
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213505"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="65d95-102">ICorDebugProcess2::GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="65d95-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="65d95-103">このプロセスで実行されている共通言語ランタイム (CLR) のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="65d95-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="65d95-104">構文</span><span class="sxs-lookup"><span data-stu-id="65d95-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="65d95-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65d95-105">Parameters</span></span>

`version`\
<span data-ttu-id="65d95-106">入出力ランタイムのバージョン番号を格納する COR_VERSION 構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="65d95-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="65d95-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="65d95-107">Remarks</span></span>

<span data-ttu-id="65d95-108">`GetVersion`プロセスにランタイムが読み込まれていない場合、メソッドはエラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="65d95-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="65d95-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="65d95-109">Requirements</span></span>

<span data-ttu-id="65d95-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65d95-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="65d95-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65d95-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="65d95-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65d95-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="65d95-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65d95-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
