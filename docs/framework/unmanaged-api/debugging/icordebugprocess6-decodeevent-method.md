---
title: ICorDebugProcess6::DecodeEvent メソッド
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: be30b1ff79c2aceb97eb4ad42052da7dd162f5d3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792285"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="2b630-102">ICorDebugProcess6::DecodeEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="2b630-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="2b630-103">特別に作成されたネイティブ例外デバッグ イベントのペイロードにカプセル化されたマネージド デバッグ イベントをデコードします。</span><span class="sxs-lookup"><span data-stu-id="2b630-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b630-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b630-104">Syntax</span></span>  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b630-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b630-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="2b630-106">[入力] マネージド デバッグ イベントに関する情報が含まれているネイティブ例外デバッグ イベントからバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2b630-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="2b630-107">[入力] `pRecord` バイト配列にある要素数。</span><span class="sxs-lookup"><span data-stu-id="2b630-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="2b630-108">からアンマネージデバッグイベントの形式を指定する[Cordebugrecordformat](cordebugrecordformat-enumeration.md)列挙体のメンバー。</span><span class="sxs-lookup"><span data-stu-id="2b630-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2b630-109">[入力] ターゲット アーキテクチャに依存し、デバッグ イベントに関する追加情報を指定するビット フィールド。</span><span class="sxs-lookup"><span data-stu-id="2b630-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="2b630-110">Windows システムの場合は、 [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md)列挙体のメンバーになることができます。</span><span class="sxs-lookup"><span data-stu-id="2b630-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="2b630-111">[入力] 例外がスローされたスレッドのオペレーティング システムの識別子。</span><span class="sxs-lookup"><span data-stu-id="2b630-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="2b630-112">入出力デコードされたマネージデバッグイベントを表す、[コードオブジェクトの](icordebugdebugevent-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2b630-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b630-113">コメント</span><span class="sxs-lookup"><span data-stu-id="2b630-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b630-114">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b630-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b630-115">要件</span><span class="sxs-lookup"><span data-stu-id="2b630-115">Requirements</span></span>  
 <span data-ttu-id="2b630-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b630-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b630-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b630-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b630-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b630-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b630-119">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b630-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b630-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b630-120">See also</span></span>

- [<span data-ttu-id="2b630-121">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b630-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="2b630-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b630-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
