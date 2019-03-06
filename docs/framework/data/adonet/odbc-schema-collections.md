---
title: ODBC スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365907"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="c444e-102">ODBC スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="c444e-102">ODBC Schema Collections</span></span>

<span data-ttu-id="c444e-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 ODBC ドライバーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c444e-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="c444e-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="c444e-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="c444e-105">Microsoft SQL Server ODBC Driver には、共通のスキーマ コレクションに加えて次の特定のスキーマ コレクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c444e-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="c444e-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="c444e-106">Tables</span></span>

- <span data-ttu-id="c444e-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="c444e-107">Indexes</span></span>

- <span data-ttu-id="c444e-108">列</span><span class="sxs-lookup"><span data-stu-id="c444e-108">Columns</span></span>

- <span data-ttu-id="c444e-109">手順</span><span class="sxs-lookup"><span data-stu-id="c444e-109">Procedures</span></span>

- <span data-ttu-id="c444e-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c444e-110">ProcedureColumns</span></span>

- <span data-ttu-id="c444e-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c444e-111">ProcedureParameters</span></span>

- <span data-ttu-id="c444e-112">ビュー</span><span class="sxs-lookup"><span data-stu-id="c444e-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="c444e-113">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="c444e-113">Tables and Views</span></span>

|<span data-ttu-id="c444e-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-114">ColumnName</span></span>|<span data-ttu-id="c444e-115">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c444e-116">TABLE_CAT</span></span>|<span data-ttu-id="c444e-117">String</span><span class="sxs-lookup"><span data-stu-id="c444e-117">String</span></span>|
|<span data-ttu-id="c444e-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c444e-118">TABLE_SCHEM</span></span>|<span data-ttu-id="c444e-119">String</span><span class="sxs-lookup"><span data-stu-id="c444e-119">String</span></span>|
|<span data-ttu-id="c444e-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-120">TABLE_NAME</span></span>|<span data-ttu-id="c444e-121">String</span><span class="sxs-lookup"><span data-stu-id="c444e-121">String</span></span>|
|<span data-ttu-id="c444e-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-122">TABLE_TYPE</span></span>|<span data-ttu-id="c444e-123">String</span><span class="sxs-lookup"><span data-stu-id="c444e-123">String</span></span>|
|<span data-ttu-id="c444e-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-124">REMARKS</span></span>|<span data-ttu-id="c444e-125">String</span><span class="sxs-lookup"><span data-stu-id="c444e-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="c444e-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="c444e-126">Indexes</span></span>

|<span data-ttu-id="c444e-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-127">ColumnName</span></span>|<span data-ttu-id="c444e-128">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c444e-129">TABLE_CAT</span></span>|<span data-ttu-id="c444e-130">String</span><span class="sxs-lookup"><span data-stu-id="c444e-130">String</span></span>|
|<span data-ttu-id="c444e-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c444e-131">TABLE_SCHEM</span></span>|<span data-ttu-id="c444e-132">String</span><span class="sxs-lookup"><span data-stu-id="c444e-132">String</span></span>|
|<span data-ttu-id="c444e-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-133">TABLE_NAME</span></span>|<span data-ttu-id="c444e-134">String</span><span class="sxs-lookup"><span data-stu-id="c444e-134">String</span></span>|
|<span data-ttu-id="c444e-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c444e-135">NON_UNIQUE</span></span>|<span data-ttu-id="c444e-136">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-136">Int16</span></span>|
|<span data-ttu-id="c444e-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="c444e-138">String</span><span class="sxs-lookup"><span data-stu-id="c444e-138">String</span></span>|
|<span data-ttu-id="c444e-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-139">INDEX_NAME</span></span>|<span data-ttu-id="c444e-140">String</span><span class="sxs-lookup"><span data-stu-id="c444e-140">String</span></span>|
|<span data-ttu-id="c444e-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-141">TYPE</span></span>|<span data-ttu-id="c444e-142">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-142">Int16</span></span>|
|<span data-ttu-id="c444e-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-144">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-144">Int16</span></span>|
|<span data-ttu-id="c444e-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-145">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-146">String</span><span class="sxs-lookup"><span data-stu-id="c444e-146">String</span></span>|
|<span data-ttu-id="c444e-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="c444e-147">ASC_OR_DESC</span></span>|<span data-ttu-id="c444e-148">String</span><span class="sxs-lookup"><span data-stu-id="c444e-148">String</span></span>|
|<span data-ttu-id="c444e-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="c444e-149">CARDINALITY</span></span>|<span data-ttu-id="c444e-150">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-150">Int32</span></span>|
|<span data-ttu-id="c444e-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="c444e-151">PAGES</span></span>|<span data-ttu-id="c444e-152">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-152">Int32</span></span>|
|<span data-ttu-id="c444e-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c444e-153">FILTER_CONDITION</span></span>|<span data-ttu-id="c444e-154">String</span><span class="sxs-lookup"><span data-stu-id="c444e-154">String</span></span>|
|<span data-ttu-id="c444e-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c444e-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c444e-156">String</span><span class="sxs-lookup"><span data-stu-id="c444e-156">String</span></span>|
|<span data-ttu-id="c444e-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="c444e-158">Byte</span><span class="sxs-lookup"><span data-stu-id="c444e-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="c444e-159">列</span><span class="sxs-lookup"><span data-stu-id="c444e-159">Columns</span></span>

|<span data-ttu-id="c444e-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-160">ColumnName</span></span>|<span data-ttu-id="c444e-161">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c444e-162">TABLE_CAT</span></span>|<span data-ttu-id="c444e-163">String</span><span class="sxs-lookup"><span data-stu-id="c444e-163">String</span></span>|
|<span data-ttu-id="c444e-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c444e-164">TABLE_SCHEM</span></span>|<span data-ttu-id="c444e-165">String</span><span class="sxs-lookup"><span data-stu-id="c444e-165">String</span></span>|
|<span data-ttu-id="c444e-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-166">TABLE_NAME</span></span>|<span data-ttu-id="c444e-167">String</span><span class="sxs-lookup"><span data-stu-id="c444e-167">String</span></span>|
|<span data-ttu-id="c444e-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-168">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-169">String</span><span class="sxs-lookup"><span data-stu-id="c444e-169">String</span></span>|
|<span data-ttu-id="c444e-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-170">DATA_TYPE</span></span>|<span data-ttu-id="c444e-171">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-171">Int16</span></span>|
|<span data-ttu-id="c444e-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-172">TYPE_NAME</span></span>|<span data-ttu-id="c444e-173">String</span><span class="sxs-lookup"><span data-stu-id="c444e-173">String</span></span>|
|<span data-ttu-id="c444e-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c444e-174">COLUMN_SIZE</span></span>|<span data-ttu-id="c444e-175">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-175">Int32</span></span>|
|<span data-ttu-id="c444e-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="c444e-177">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-177">Int32</span></span>|
|<span data-ttu-id="c444e-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c444e-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c444e-179">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-179">Int16</span></span>|
|<span data-ttu-id="c444e-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c444e-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c444e-181">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-181">Int16</span></span>|
|<span data-ttu-id="c444e-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-182">NULLABLE</span></span>|<span data-ttu-id="c444e-183">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-183">Int16</span></span>|
|<span data-ttu-id="c444e-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-184">REMARKS</span></span>|<span data-ttu-id="c444e-185">String</span><span class="sxs-lookup"><span data-stu-id="c444e-185">String</span></span>|
|<span data-ttu-id="c444e-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c444e-186">COLUMN_DEF</span></span>|<span data-ttu-id="c444e-187">String</span><span class="sxs-lookup"><span data-stu-id="c444e-187">String</span></span>|
|<span data-ttu-id="c444e-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c444e-189">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-189">Int16</span></span>|
|<span data-ttu-id="c444e-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c444e-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c444e-191">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-191">Int16</span></span>|
|<span data-ttu-id="c444e-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c444e-193">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-193">Int32</span></span>|
|<span data-ttu-id="c444e-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-195">Int32</span></span>|
|<span data-ttu-id="c444e-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-196">IS_NULLABLE</span></span>|<span data-ttu-id="c444e-197">String</span><span class="sxs-lookup"><span data-stu-id="c444e-197">String</span></span>|
|<span data-ttu-id="c444e-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c444e-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c444e-199">String</span><span class="sxs-lookup"><span data-stu-id="c444e-199">String</span></span>|
|<span data-ttu-id="c444e-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c444e-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c444e-201">String</span><span class="sxs-lookup"><span data-stu-id="c444e-201">String</span></span>|
|<span data-ttu-id="c444e-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="c444e-203">Byte</span><span class="sxs-lookup"><span data-stu-id="c444e-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="c444e-204">手順</span><span class="sxs-lookup"><span data-stu-id="c444e-204">Procedures</span></span>

|<span data-ttu-id="c444e-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-205">ColumnName</span></span>|<span data-ttu-id="c444e-206">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c444e-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="c444e-208">String</span><span class="sxs-lookup"><span data-stu-id="c444e-208">String</span></span>|
|<span data-ttu-id="c444e-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c444e-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c444e-210">String</span><span class="sxs-lookup"><span data-stu-id="c444e-210">String</span></span>|
|<span data-ttu-id="c444e-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="c444e-212">String</span><span class="sxs-lookup"><span data-stu-id="c444e-212">String</span></span>|
|<span data-ttu-id="c444e-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c444e-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c444e-214">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-214">Int32</span></span>|
|<span data-ttu-id="c444e-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c444e-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c444e-216">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-216">Int32</span></span>|
|<span data-ttu-id="c444e-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c444e-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c444e-218">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-218">Int32</span></span>|
|<span data-ttu-id="c444e-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-219">REMARKS</span></span>|<span data-ttu-id="c444e-220">String</span><span class="sxs-lookup"><span data-stu-id="c444e-220">String</span></span>|
|<span data-ttu-id="c444e-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c444e-222">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="c444e-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c444e-223">ProcedureColumns</span></span>

|<span data-ttu-id="c444e-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-224">ColumnName</span></span>|<span data-ttu-id="c444e-225">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c444e-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="c444e-227">String</span><span class="sxs-lookup"><span data-stu-id="c444e-227">String</span></span>|
|<span data-ttu-id="c444e-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c444e-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c444e-229">String</span><span class="sxs-lookup"><span data-stu-id="c444e-229">String</span></span>|
|<span data-ttu-id="c444e-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="c444e-231">String</span><span class="sxs-lookup"><span data-stu-id="c444e-231">String</span></span>|
|<span data-ttu-id="c444e-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-232">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-233">String</span><span class="sxs-lookup"><span data-stu-id="c444e-233">String</span></span>|
|<span data-ttu-id="c444e-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-234">COLUMN_TYPE</span></span>|<span data-ttu-id="c444e-235">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-235">Int16</span></span>|
|<span data-ttu-id="c444e-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-236">DATA_TYPE</span></span>|<span data-ttu-id="c444e-237">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-237">Int16</span></span>|
|<span data-ttu-id="c444e-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-238">TYPE_NAME</span></span>|<span data-ttu-id="c444e-239">String</span><span class="sxs-lookup"><span data-stu-id="c444e-239">String</span></span>|
|<span data-ttu-id="c444e-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c444e-240">COLUMN_SIZE</span></span>|<span data-ttu-id="c444e-241">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-241">Int32</span></span>|
|<span data-ttu-id="c444e-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="c444e-243">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-243">Int32</span></span>|
|<span data-ttu-id="c444e-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c444e-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c444e-245">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-245">Int16</span></span>|
|<span data-ttu-id="c444e-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c444e-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c444e-247">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-247">Int16</span></span>|
|<span data-ttu-id="c444e-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-248">NULLABLE</span></span>|<span data-ttu-id="c444e-249">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-249">Int16</span></span>|
|<span data-ttu-id="c444e-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-250">REMARKS</span></span>|<span data-ttu-id="c444e-251">String</span><span class="sxs-lookup"><span data-stu-id="c444e-251">String</span></span>|
|<span data-ttu-id="c444e-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c444e-252">COLUMN_DEF</span></span>|<span data-ttu-id="c444e-253">String</span><span class="sxs-lookup"><span data-stu-id="c444e-253">String</span></span>|
|<span data-ttu-id="c444e-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c444e-255">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-255">Int16</span></span>|
|<span data-ttu-id="c444e-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c444e-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c444e-257">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-257">Int16</span></span>|
|<span data-ttu-id="c444e-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c444e-259">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-259">Int32</span></span>|
|<span data-ttu-id="c444e-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-261">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-261">Int32</span></span>|
|<span data-ttu-id="c444e-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-262">IS_NULLABLE</span></span>|<span data-ttu-id="c444e-263">String</span><span class="sxs-lookup"><span data-stu-id="c444e-263">String</span></span>|
|<span data-ttu-id="c444e-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c444e-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c444e-265">String</span><span class="sxs-lookup"><span data-stu-id="c444e-265">String</span></span>|
|<span data-ttu-id="c444e-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c444e-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c444e-267">String</span><span class="sxs-lookup"><span data-stu-id="c444e-267">String</span></span>|
|<span data-ttu-id="c444e-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="c444e-269">Byte</span><span class="sxs-lookup"><span data-stu-id="c444e-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="c444e-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c444e-270">ProcedureParameters</span></span>

|<span data-ttu-id="c444e-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-271">ColumnName</span></span>|<span data-ttu-id="c444e-272">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c444e-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="c444e-274">String</span><span class="sxs-lookup"><span data-stu-id="c444e-274">String</span></span>|
|<span data-ttu-id="c444e-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c444e-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c444e-276">String</span><span class="sxs-lookup"><span data-stu-id="c444e-276">String</span></span>|
|<span data-ttu-id="c444e-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="c444e-278">String</span><span class="sxs-lookup"><span data-stu-id="c444e-278">String</span></span>|
|<span data-ttu-id="c444e-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-279">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-280">String</span><span class="sxs-lookup"><span data-stu-id="c444e-280">String</span></span>|
|<span data-ttu-id="c444e-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-281">COLUMN_TYPE</span></span>|<span data-ttu-id="c444e-282">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-282">Int16</span></span>|
|<span data-ttu-id="c444e-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-283">DATA_TYPE</span></span>|<span data-ttu-id="c444e-284">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-284">Int16</span></span>|
|<span data-ttu-id="c444e-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-285">TYPE_NAME</span></span>|<span data-ttu-id="c444e-286">String</span><span class="sxs-lookup"><span data-stu-id="c444e-286">String</span></span>|
|<span data-ttu-id="c444e-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c444e-287">COLUMN_SIZE</span></span>|<span data-ttu-id="c444e-288">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-288">Int32</span></span>|
|<span data-ttu-id="c444e-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="c444e-290">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-290">Int32</span></span>|
|<span data-ttu-id="c444e-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c444e-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c444e-292">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-292">Int16</span></span>|
|<span data-ttu-id="c444e-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c444e-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c444e-294">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-294">Int16</span></span>|
|<span data-ttu-id="c444e-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-295">NULLABLE</span></span>|<span data-ttu-id="c444e-296">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-296">Int16</span></span>|
|<span data-ttu-id="c444e-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-297">REMARKS</span></span>|<span data-ttu-id="c444e-298">String</span><span class="sxs-lookup"><span data-stu-id="c444e-298">String</span></span>|
|<span data-ttu-id="c444e-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c444e-299">COLUMN_DEF</span></span>|<span data-ttu-id="c444e-300">String</span><span class="sxs-lookup"><span data-stu-id="c444e-300">String</span></span>|
|<span data-ttu-id="c444e-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c444e-302">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-302">Int16</span></span>|
|<span data-ttu-id="c444e-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c444e-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c444e-304">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-304">Int16</span></span>|
|<span data-ttu-id="c444e-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c444e-306">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-306">Int32</span></span>|
|<span data-ttu-id="c444e-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-308">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-308">Int32</span></span>|
|<span data-ttu-id="c444e-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-309">IS_NULLABLE</span></span>|<span data-ttu-id="c444e-310">String</span><span class="sxs-lookup"><span data-stu-id="c444e-310">String</span></span>|
|<span data-ttu-id="c444e-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c444e-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c444e-312">String</span><span class="sxs-lookup"><span data-stu-id="c444e-312">String</span></span>|
|<span data-ttu-id="c444e-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c444e-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c444e-314">String</span><span class="sxs-lookup"><span data-stu-id="c444e-314">String</span></span>|
|<span data-ttu-id="c444e-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="c444e-316">Byte</span><span class="sxs-lookup"><span data-stu-id="c444e-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="c444e-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="c444e-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="c444e-318">Microsoft SQL Server Oracle ODBC ドライバーは、共通のスキーマ コレクションに加えて次の特定のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c444e-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="c444e-319">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="c444e-319">Tables</span></span>

- <span data-ttu-id="c444e-320">列</span><span class="sxs-lookup"><span data-stu-id="c444e-320">Columns</span></span>

- <span data-ttu-id="c444e-321">手順</span><span class="sxs-lookup"><span data-stu-id="c444e-321">Procedures</span></span>

- <span data-ttu-id="c444e-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c444e-322">ProcedureColumns</span></span>

- <span data-ttu-id="c444e-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c444e-323">ProcedureParameters</span></span>

- <span data-ttu-id="c444e-324">ビュー</span><span class="sxs-lookup"><span data-stu-id="c444e-324">Views</span></span>

- <span data-ttu-id="c444e-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="c444e-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="c444e-326">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="c444e-326">Tables and Views</span></span>

|<span data-ttu-id="c444e-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-327">ColumnName</span></span>|<span data-ttu-id="c444e-328">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c444e-330">String</span><span class="sxs-lookup"><span data-stu-id="c444e-330">String</span></span>|
|<span data-ttu-id="c444e-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c444e-331">TABLE_OWNER</span></span>|<span data-ttu-id="c444e-332">String</span><span class="sxs-lookup"><span data-stu-id="c444e-332">String</span></span>|
|<span data-ttu-id="c444e-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-333">TABLE_NAME</span></span>|<span data-ttu-id="c444e-334">String</span><span class="sxs-lookup"><span data-stu-id="c444e-334">String</span></span>|
|<span data-ttu-id="c444e-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-335">TABLE_TYPE</span></span>|<span data-ttu-id="c444e-336">String</span><span class="sxs-lookup"><span data-stu-id="c444e-336">String</span></span>|
|<span data-ttu-id="c444e-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-337">REMARKS</span></span>|<span data-ttu-id="c444e-338">String</span><span class="sxs-lookup"><span data-stu-id="c444e-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="c444e-339">列</span><span class="sxs-lookup"><span data-stu-id="c444e-339">Columns</span></span>

|<span data-ttu-id="c444e-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-340">ColumnName</span></span>|<span data-ttu-id="c444e-341">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c444e-343">String</span><span class="sxs-lookup"><span data-stu-id="c444e-343">String</span></span>|
|<span data-ttu-id="c444e-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c444e-344">TABLE_OWNER</span></span>|<span data-ttu-id="c444e-345">String</span><span class="sxs-lookup"><span data-stu-id="c444e-345">String</span></span>|
|<span data-ttu-id="c444e-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-346">TABLE_NAME</span></span>|<span data-ttu-id="c444e-347">String</span><span class="sxs-lookup"><span data-stu-id="c444e-347">String</span></span>|
|<span data-ttu-id="c444e-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-348">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-349">String</span><span class="sxs-lookup"><span data-stu-id="c444e-349">String</span></span>|
|<span data-ttu-id="c444e-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-350">DATA_TYPE</span></span>|<span data-ttu-id="c444e-351">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-351">Int16</span></span>|
|<span data-ttu-id="c444e-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-352">TYPE_NAME</span></span>|<span data-ttu-id="c444e-353">String</span><span class="sxs-lookup"><span data-stu-id="c444e-353">String</span></span>|
|<span data-ttu-id="c444e-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c444e-354">PRECISION</span></span>|<span data-ttu-id="c444e-355">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-355">Int32</span></span>|
|<span data-ttu-id="c444e-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-356">LENGTH</span></span>|<span data-ttu-id="c444e-357">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-357">Int32</span></span>|
|<span data-ttu-id="c444e-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="c444e-358">SCALE</span></span>|<span data-ttu-id="c444e-359">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-359">Int16</span></span>|
|<span data-ttu-id="c444e-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="c444e-360">RADIX</span></span>|<span data-ttu-id="c444e-361">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-361">Int16</span></span>|
|<span data-ttu-id="c444e-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-362">NULLABLE</span></span>|<span data-ttu-id="c444e-363">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-363">Int16</span></span>|
|<span data-ttu-id="c444e-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-364">REMARKS</span></span>|<span data-ttu-id="c444e-365">String</span><span class="sxs-lookup"><span data-stu-id="c444e-365">String</span></span>|
|<span data-ttu-id="c444e-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-367">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="c444e-368">手順</span><span class="sxs-lookup"><span data-stu-id="c444e-368">Procedures</span></span>

|<span data-ttu-id="c444e-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-369">ColumnName</span></span>|<span data-ttu-id="c444e-370">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c444e-372">String</span><span class="sxs-lookup"><span data-stu-id="c444e-372">String</span></span>|
|<span data-ttu-id="c444e-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c444e-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c444e-374">String</span><span class="sxs-lookup"><span data-stu-id="c444e-374">String</span></span>|
|<span data-ttu-id="c444e-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="c444e-376">String</span><span class="sxs-lookup"><span data-stu-id="c444e-376">String</span></span>|
|<span data-ttu-id="c444e-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c444e-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c444e-378">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-378">Int16</span></span>|
|<span data-ttu-id="c444e-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c444e-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c444e-380">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-380">Int16</span></span>|
|<span data-ttu-id="c444e-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c444e-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c444e-382">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-382">Int16</span></span>|
|<span data-ttu-id="c444e-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-383">REMARKS</span></span>|<span data-ttu-id="c444e-384">String</span><span class="sxs-lookup"><span data-stu-id="c444e-384">String</span></span>|
|<span data-ttu-id="c444e-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c444e-386">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="c444e-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c444e-387">ProcedureColumns</span></span>

|<span data-ttu-id="c444e-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-388">ColumnName</span></span>|<span data-ttu-id="c444e-389">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c444e-391">String</span><span class="sxs-lookup"><span data-stu-id="c444e-391">String</span></span>|
|<span data-ttu-id="c444e-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c444e-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c444e-393">String</span><span class="sxs-lookup"><span data-stu-id="c444e-393">String</span></span>|
|<span data-ttu-id="c444e-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="c444e-395">String</span><span class="sxs-lookup"><span data-stu-id="c444e-395">String</span></span>|
|<span data-ttu-id="c444e-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-396">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-397">String</span><span class="sxs-lookup"><span data-stu-id="c444e-397">String</span></span>|
|<span data-ttu-id="c444e-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-398">COLUMN_TYPE</span></span>|<span data-ttu-id="c444e-399">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-399">Int16</span></span>|
|<span data-ttu-id="c444e-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-400">DATA_TYPE</span></span>|<span data-ttu-id="c444e-401">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-401">Int16</span></span>|
|<span data-ttu-id="c444e-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-402">TYPE_NAME</span></span>|<span data-ttu-id="c444e-403">String</span><span class="sxs-lookup"><span data-stu-id="c444e-403">String</span></span>|
|<span data-ttu-id="c444e-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c444e-404">PRECISION</span></span>|<span data-ttu-id="c444e-405">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-405">Int32</span></span>|
|<span data-ttu-id="c444e-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-406">LENGTH</span></span>|<span data-ttu-id="c444e-407">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-407">Int32</span></span>|
|<span data-ttu-id="c444e-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="c444e-408">SCALE</span></span>|<span data-ttu-id="c444e-409">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-409">Int16</span></span>|
|<span data-ttu-id="c444e-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="c444e-410">RADIX</span></span>|<span data-ttu-id="c444e-411">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-411">Int16</span></span>|
|<span data-ttu-id="c444e-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-412">NULLABLE</span></span>|<span data-ttu-id="c444e-413">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-413">Int16</span></span>|
|<span data-ttu-id="c444e-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-414">REMARKS</span></span>|<span data-ttu-id="c444e-415">String</span><span class="sxs-lookup"><span data-stu-id="c444e-415">String</span></span>|
|<span data-ttu-id="c444e-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="c444e-416">OVERLOAD</span></span>|<span data-ttu-id="c444e-417">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-417">Int32</span></span>|
|<span data-ttu-id="c444e-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-419">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="c444e-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="c444e-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="c444e-421">Microsoft Jet ODBC Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c444e-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="c444e-422">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="c444e-422">Tables</span></span>

- <span data-ttu-id="c444e-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="c444e-423">Indexes</span></span>

- <span data-ttu-id="c444e-424">列</span><span class="sxs-lookup"><span data-stu-id="c444e-424">Columns</span></span>

- <span data-ttu-id="c444e-425">手順</span><span class="sxs-lookup"><span data-stu-id="c444e-425">Procedures</span></span>

- <span data-ttu-id="c444e-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c444e-426">ProcedureColumns</span></span>

- <span data-ttu-id="c444e-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c444e-427">ProcedureParameters</span></span>

- <span data-ttu-id="c444e-428">ビュー</span><span class="sxs-lookup"><span data-stu-id="c444e-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="c444e-429">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="c444e-429">Tables and Views</span></span>

|<span data-ttu-id="c444e-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-430">ColumnName</span></span>|<span data-ttu-id="c444e-431">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c444e-433">String</span><span class="sxs-lookup"><span data-stu-id="c444e-433">String</span></span>|
|<span data-ttu-id="c444e-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c444e-434">TABLE_OWNER</span></span>|<span data-ttu-id="c444e-435">String</span><span class="sxs-lookup"><span data-stu-id="c444e-435">String</span></span>|
|<span data-ttu-id="c444e-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-436">TABLE_NAME</span></span>|<span data-ttu-id="c444e-437">String</span><span class="sxs-lookup"><span data-stu-id="c444e-437">String</span></span>|
|<span data-ttu-id="c444e-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-438">TABLE_TYPE</span></span>|<span data-ttu-id="c444e-439">String</span><span class="sxs-lookup"><span data-stu-id="c444e-439">String</span></span>|
|<span data-ttu-id="c444e-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-440">REMARKS</span></span>|<span data-ttu-id="c444e-441">String</span><span class="sxs-lookup"><span data-stu-id="c444e-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="c444e-442">列</span><span class="sxs-lookup"><span data-stu-id="c444e-442">Columns</span></span>

|<span data-ttu-id="c444e-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-443">ColumnName</span></span>|<span data-ttu-id="c444e-444">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c444e-446">String</span><span class="sxs-lookup"><span data-stu-id="c444e-446">String</span></span>|
|<span data-ttu-id="c444e-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c444e-447">TABLE_OWNER</span></span>|<span data-ttu-id="c444e-448">String</span><span class="sxs-lookup"><span data-stu-id="c444e-448">String</span></span>|
|<span data-ttu-id="c444e-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-449">TABLE_NAME</span></span>|<span data-ttu-id="c444e-450">String</span><span class="sxs-lookup"><span data-stu-id="c444e-450">String</span></span>|
|<span data-ttu-id="c444e-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-451">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-452">String</span><span class="sxs-lookup"><span data-stu-id="c444e-452">String</span></span>|
|<span data-ttu-id="c444e-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-453">DATA_TYPE</span></span>|<span data-ttu-id="c444e-454">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-454">Int16</span></span>|
|<span data-ttu-id="c444e-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-455">TYPE_NAME</span></span>|<span data-ttu-id="c444e-456">String</span><span class="sxs-lookup"><span data-stu-id="c444e-456">String</span></span>|
|<span data-ttu-id="c444e-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c444e-457">PRECISION</span></span>|<span data-ttu-id="c444e-458">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-458">Int32</span></span>|
|<span data-ttu-id="c444e-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-459">LENGTH</span></span>|<span data-ttu-id="c444e-460">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-460">Int32</span></span>|
|<span data-ttu-id="c444e-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="c444e-461">SCALE</span></span>|<span data-ttu-id="c444e-462">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-462">Int16</span></span>|
|<span data-ttu-id="c444e-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="c444e-463">RADIX</span></span>|<span data-ttu-id="c444e-464">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-464">Int16</span></span>|
|<span data-ttu-id="c444e-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-465">NULLABLE</span></span>|<span data-ttu-id="c444e-466">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-466">Int16</span></span>|
|<span data-ttu-id="c444e-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-467">REMARKS</span></span>|<span data-ttu-id="c444e-468">String</span><span class="sxs-lookup"><span data-stu-id="c444e-468">String</span></span>|
|<span data-ttu-id="c444e-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-470">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="c444e-471">手順</span><span class="sxs-lookup"><span data-stu-id="c444e-471">Procedures</span></span>

|<span data-ttu-id="c444e-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-472">ColumnName</span></span>|<span data-ttu-id="c444e-473">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c444e-475">String</span><span class="sxs-lookup"><span data-stu-id="c444e-475">String</span></span>|
|<span data-ttu-id="c444e-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c444e-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c444e-477">String</span><span class="sxs-lookup"><span data-stu-id="c444e-477">String</span></span>|
|<span data-ttu-id="c444e-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="c444e-479">String</span><span class="sxs-lookup"><span data-stu-id="c444e-479">String</span></span>|
|<span data-ttu-id="c444e-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c444e-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c444e-481">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-481">Int16</span></span>|
|<span data-ttu-id="c444e-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c444e-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c444e-483">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-483">Int16</span></span>|
|<span data-ttu-id="c444e-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c444e-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c444e-485">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-485">Int16</span></span>|
|<span data-ttu-id="c444e-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-486">REMARKS</span></span>|<span data-ttu-id="c444e-487">String</span><span class="sxs-lookup"><span data-stu-id="c444e-487">String</span></span>|
|<span data-ttu-id="c444e-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c444e-489">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="c444e-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c444e-490">ProcedureColumns</span></span>

|<span data-ttu-id="c444e-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-491">ColumnName</span></span>|<span data-ttu-id="c444e-492">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c444e-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c444e-494">String</span><span class="sxs-lookup"><span data-stu-id="c444e-494">String</span></span>|
|<span data-ttu-id="c444e-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c444e-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c444e-496">String</span><span class="sxs-lookup"><span data-stu-id="c444e-496">String</span></span>|
|<span data-ttu-id="c444e-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="c444e-498">String</span><span class="sxs-lookup"><span data-stu-id="c444e-498">String</span></span>|
|<span data-ttu-id="c444e-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-499">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-500">String</span><span class="sxs-lookup"><span data-stu-id="c444e-500">String</span></span>|
|<span data-ttu-id="c444e-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-501">COLUMN_TYPE</span></span>|<span data-ttu-id="c444e-502">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-502">Int16</span></span>|
|<span data-ttu-id="c444e-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-503">DATA_TYPE</span></span>|<span data-ttu-id="c444e-504">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-504">Int16</span></span>|
|<span data-ttu-id="c444e-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-505">TYPE_NAME</span></span>|<span data-ttu-id="c444e-506">String</span><span class="sxs-lookup"><span data-stu-id="c444e-506">String</span></span>|
|<span data-ttu-id="c444e-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c444e-507">PRECISION</span></span>|<span data-ttu-id="c444e-508">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-508">Int32</span></span>|
|<span data-ttu-id="c444e-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-509">LENGTH</span></span>|<span data-ttu-id="c444e-510">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-510">Int32</span></span>|
|<span data-ttu-id="c444e-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="c444e-511">SCALE</span></span>|<span data-ttu-id="c444e-512">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-512">Int16</span></span>|
|<span data-ttu-id="c444e-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="c444e-513">RADIX</span></span>|<span data-ttu-id="c444e-514">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-514">Int16</span></span>|
|<span data-ttu-id="c444e-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-515">NULLABLE</span></span>|<span data-ttu-id="c444e-516">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-516">Int16</span></span>|
|<span data-ttu-id="c444e-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-517">REMARKS</span></span>|<span data-ttu-id="c444e-518">String</span><span class="sxs-lookup"><span data-stu-id="c444e-518">String</span></span>|
|<span data-ttu-id="c444e-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="c444e-519">OVERLOAD</span></span>|<span data-ttu-id="c444e-520">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-520">Int32</span></span>|
|<span data-ttu-id="c444e-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-522">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="c444e-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c444e-523">ProcedureParameters</span></span>

|<span data-ttu-id="c444e-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c444e-524">ColumnName</span></span>|<span data-ttu-id="c444e-525">DataType</span><span class="sxs-lookup"><span data-stu-id="c444e-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="c444e-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c444e-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="c444e-527">String</span><span class="sxs-lookup"><span data-stu-id="c444e-527">String</span></span>|
|<span data-ttu-id="c444e-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c444e-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c444e-529">String</span><span class="sxs-lookup"><span data-stu-id="c444e-529">String</span></span>|
|<span data-ttu-id="c444e-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="c444e-531">String</span><span class="sxs-lookup"><span data-stu-id="c444e-531">String</span></span>|
|<span data-ttu-id="c444e-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-532">COLUMN_NAME</span></span>|<span data-ttu-id="c444e-533">String</span><span class="sxs-lookup"><span data-stu-id="c444e-533">String</span></span>|
|<span data-ttu-id="c444e-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-534">COLUMN_TYPE</span></span>|<span data-ttu-id="c444e-535">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-535">Int16</span></span>|
|<span data-ttu-id="c444e-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-536">DATA_TYPE</span></span>|<span data-ttu-id="c444e-537">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-537">Int16</span></span>|
|<span data-ttu-id="c444e-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c444e-538">TYPE_NAME</span></span>|<span data-ttu-id="c444e-539">String</span><span class="sxs-lookup"><span data-stu-id="c444e-539">String</span></span>|
|<span data-ttu-id="c444e-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c444e-540">COLUMN_SIZE</span></span>|<span data-ttu-id="c444e-541">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-541">Int32</span></span>|
|<span data-ttu-id="c444e-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="c444e-543">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-543">Int32</span></span>|
|<span data-ttu-id="c444e-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c444e-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c444e-545">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-545">Int16</span></span>|
|<span data-ttu-id="c444e-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c444e-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c444e-547">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-547">Int16</span></span>|
|<span data-ttu-id="c444e-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-548">NULLABLE</span></span>|<span data-ttu-id="c444e-549">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-549">Int16</span></span>|
|<span data-ttu-id="c444e-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c444e-550">REMARKS</span></span>|<span data-ttu-id="c444e-551">String</span><span class="sxs-lookup"><span data-stu-id="c444e-551">String</span></span>|
|<span data-ttu-id="c444e-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c444e-552">COLUMN_DEF</span></span>|<span data-ttu-id="c444e-553">String</span><span class="sxs-lookup"><span data-stu-id="c444e-553">String</span></span>|
|<span data-ttu-id="c444e-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c444e-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c444e-555">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-555">Int16</span></span>|
|<span data-ttu-id="c444e-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c444e-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c444e-557">Int16</span><span class="sxs-lookup"><span data-stu-id="c444e-557">Int16</span></span>|
|<span data-ttu-id="c444e-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c444e-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c444e-559">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-559">Int32</span></span>|
|<span data-ttu-id="c444e-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c444e-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="c444e-561">Int32</span><span class="sxs-lookup"><span data-stu-id="c444e-561">Int32</span></span>|
|<span data-ttu-id="c444e-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c444e-562">IS_NULLABLE</span></span>|<span data-ttu-id="c444e-563">String</span><span class="sxs-lookup"><span data-stu-id="c444e-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="c444e-564">関連項目</span><span class="sxs-lookup"><span data-stu-id="c444e-564">See also</span></span>

- [<span data-ttu-id="c444e-565">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="c444e-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
