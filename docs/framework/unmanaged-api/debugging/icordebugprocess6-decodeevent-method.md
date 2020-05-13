---
title: ICorDebugProcess6::DecodeEvent メソッド
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: 7c163311f9ce8f3d98ce72f45165a5e517c6c0aa
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205513"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="22f43-102">ICorDebugProcess6::DecodeEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="22f43-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="22f43-103">特別に作成されたネイティブ例外デバッグ イベントのペイロードにカプセル化されたマネージド デバッグ イベントをデコードします。</span><span class="sxs-lookup"><span data-stu-id="22f43-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f43-104">構文</span><span class="sxs-lookup"><span data-stu-id="22f43-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="22f43-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22f43-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="22f43-106">[入力] マネージド デバッグ イベントに関する情報が含まれているネイティブ例外デバッグ イベントからバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="22f43-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="22f43-107">[入力] `pRecord` バイト配列にある要素数。</span><span class="sxs-lookup"><span data-stu-id="22f43-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="22f43-108">からアンマネージデバッグイベントの形式を指定する[Cordebugrecordformat](cordebugrecordformat-enumeration.md)列挙体のメンバー。</span><span class="sxs-lookup"><span data-stu-id="22f43-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="22f43-109">[入力] ターゲット アーキテクチャに依存し、デバッグ イベントに関する追加情報を指定するビット フィールド。</span><span class="sxs-lookup"><span data-stu-id="22f43-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="22f43-110">Windows システムの場合は、 [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md)列挙体のメンバーになることができます。</span><span class="sxs-lookup"><span data-stu-id="22f43-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="22f43-111">[入力] 例外がスローされたスレッドのオペレーティング システムの識別子。</span><span class="sxs-lookup"><span data-stu-id="22f43-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="22f43-112">入出力デコードされたマネージデバッグイベントを表す、[コードオブジェクトの](icordebugdebugevent-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="22f43-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22f43-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="22f43-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22f43-114">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="22f43-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f43-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="22f43-115">Requirements</span></span>  
 <span data-ttu-id="22f43-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f43-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22f43-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22f43-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22f43-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22f43-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22f43-119">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22f43-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f43-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="22f43-120">See also</span></span>

- [<span data-ttu-id="22f43-121">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22f43-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="22f43-122">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="22f43-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
