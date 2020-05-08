---
title: ODBC スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794719"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="309b6-102">ODBC スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="309b6-102">ODBC Schema Collections</span></span>

<span data-ttu-id="309b6-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 ODBC ドライバーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="309b6-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="309b6-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="309b6-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="309b6-105">Microsoft SQL Server ODBC Driver では、共通のスキーマ コレクションに加えて次のスキーマ コレクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="309b6-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="309b6-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="309b6-106">Tables</span></span>

- <span data-ttu-id="309b6-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="309b6-107">Indexes</span></span>

- <span data-ttu-id="309b6-108">列</span><span class="sxs-lookup"><span data-stu-id="309b6-108">Columns</span></span>

- <span data-ttu-id="309b6-109">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="309b6-109">Procedures</span></span>

- <span data-ttu-id="309b6-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309b6-110">ProcedureColumns</span></span>

- <span data-ttu-id="309b6-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309b6-111">ProcedureParameters</span></span>

- <span data-ttu-id="309b6-112">Views</span><span class="sxs-lookup"><span data-stu-id="309b6-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="309b6-113">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="309b6-113">Tables and Views</span></span>

|<span data-ttu-id="309b6-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-114">ColumnName</span></span>|<span data-ttu-id="309b6-115">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="309b6-116">TABLE_CAT</span></span>|<span data-ttu-id="309b6-117">String</span><span class="sxs-lookup"><span data-stu-id="309b6-117">String</span></span>|
|<span data-ttu-id="309b6-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309b6-118">TABLE_SCHEM</span></span>|<span data-ttu-id="309b6-119">String</span><span class="sxs-lookup"><span data-stu-id="309b6-119">String</span></span>|
|<span data-ttu-id="309b6-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-120">TABLE_NAME</span></span>|<span data-ttu-id="309b6-121">String</span><span class="sxs-lookup"><span data-stu-id="309b6-121">String</span></span>|
|<span data-ttu-id="309b6-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-122">TABLE_TYPE</span></span>|<span data-ttu-id="309b6-123">String</span><span class="sxs-lookup"><span data-stu-id="309b6-123">String</span></span>|
|<span data-ttu-id="309b6-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-124">REMARKS</span></span>|<span data-ttu-id="309b6-125">String</span><span class="sxs-lookup"><span data-stu-id="309b6-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="309b6-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="309b6-126">Indexes</span></span>

|<span data-ttu-id="309b6-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-127">ColumnName</span></span>|<span data-ttu-id="309b6-128">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="309b6-129">TABLE_CAT</span></span>|<span data-ttu-id="309b6-130">String</span><span class="sxs-lookup"><span data-stu-id="309b6-130">String</span></span>|
|<span data-ttu-id="309b6-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309b6-131">TABLE_SCHEM</span></span>|<span data-ttu-id="309b6-132">String</span><span class="sxs-lookup"><span data-stu-id="309b6-132">String</span></span>|
|<span data-ttu-id="309b6-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-133">TABLE_NAME</span></span>|<span data-ttu-id="309b6-134">String</span><span class="sxs-lookup"><span data-stu-id="309b6-134">String</span></span>|
|<span data-ttu-id="309b6-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="309b6-135">NON_UNIQUE</span></span>|<span data-ttu-id="309b6-136">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-136">Int16</span></span>|
|<span data-ttu-id="309b6-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="309b6-138">String</span><span class="sxs-lookup"><span data-stu-id="309b6-138">String</span></span>|
|<span data-ttu-id="309b6-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-139">INDEX_NAME</span></span>|<span data-ttu-id="309b6-140">String</span><span class="sxs-lookup"><span data-stu-id="309b6-140">String</span></span>|
|<span data-ttu-id="309b6-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-141">TYPE</span></span>|<span data-ttu-id="309b6-142">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-142">Int16</span></span>|
|<span data-ttu-id="309b6-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-144">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-144">Int16</span></span>|
|<span data-ttu-id="309b6-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-145">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-146">String</span><span class="sxs-lookup"><span data-stu-id="309b6-146">String</span></span>|
|<span data-ttu-id="309b6-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="309b6-147">ASC_OR_DESC</span></span>|<span data-ttu-id="309b6-148">String</span><span class="sxs-lookup"><span data-stu-id="309b6-148">String</span></span>|
|<span data-ttu-id="309b6-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="309b6-149">CARDINALITY</span></span>|<span data-ttu-id="309b6-150">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-150">Int32</span></span>|
|<span data-ttu-id="309b6-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="309b6-151">PAGES</span></span>|<span data-ttu-id="309b6-152">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-152">Int32</span></span>|
|<span data-ttu-id="309b6-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="309b6-153">FILTER_CONDITION</span></span>|<span data-ttu-id="309b6-154">String</span><span class="sxs-lookup"><span data-stu-id="309b6-154">String</span></span>|
|<span data-ttu-id="309b6-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="309b6-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="309b6-156">String</span><span class="sxs-lookup"><span data-stu-id="309b6-156">String</span></span>|
|<span data-ttu-id="309b6-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="309b6-158">Byte</span><span class="sxs-lookup"><span data-stu-id="309b6-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="309b6-159">列</span><span class="sxs-lookup"><span data-stu-id="309b6-159">Columns</span></span>

|<span data-ttu-id="309b6-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-160">ColumnName</span></span>|<span data-ttu-id="309b6-161">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="309b6-162">TABLE_CAT</span></span>|<span data-ttu-id="309b6-163">String</span><span class="sxs-lookup"><span data-stu-id="309b6-163">String</span></span>|
|<span data-ttu-id="309b6-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309b6-164">TABLE_SCHEM</span></span>|<span data-ttu-id="309b6-165">String</span><span class="sxs-lookup"><span data-stu-id="309b6-165">String</span></span>|
|<span data-ttu-id="309b6-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-166">TABLE_NAME</span></span>|<span data-ttu-id="309b6-167">String</span><span class="sxs-lookup"><span data-stu-id="309b6-167">String</span></span>|
|<span data-ttu-id="309b6-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-168">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-169">String</span><span class="sxs-lookup"><span data-stu-id="309b6-169">String</span></span>|
|<span data-ttu-id="309b6-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-170">DATA_TYPE</span></span>|<span data-ttu-id="309b6-171">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-171">Int16</span></span>|
|<span data-ttu-id="309b6-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-172">TYPE_NAME</span></span>|<span data-ttu-id="309b6-173">String</span><span class="sxs-lookup"><span data-stu-id="309b6-173">String</span></span>|
|<span data-ttu-id="309b6-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="309b6-174">COLUMN_SIZE</span></span>|<span data-ttu-id="309b6-175">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-175">Int32</span></span>|
|<span data-ttu-id="309b6-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="309b6-177">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-177">Int32</span></span>|
|<span data-ttu-id="309b6-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="309b6-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="309b6-179">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-179">Int16</span></span>|
|<span data-ttu-id="309b6-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="309b6-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="309b6-181">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-181">Int16</span></span>|
|<span data-ttu-id="309b6-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-182">NULLABLE</span></span>|<span data-ttu-id="309b6-183">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-183">Int16</span></span>|
|<span data-ttu-id="309b6-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-184">REMARKS</span></span>|<span data-ttu-id="309b6-185">String</span><span class="sxs-lookup"><span data-stu-id="309b6-185">String</span></span>|
|<span data-ttu-id="309b6-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="309b6-186">COLUMN_DEF</span></span>|<span data-ttu-id="309b6-187">String</span><span class="sxs-lookup"><span data-stu-id="309b6-187">String</span></span>|
|<span data-ttu-id="309b6-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="309b6-189">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-189">Int16</span></span>|
|<span data-ttu-id="309b6-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="309b6-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="309b6-191">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-191">Int16</span></span>|
|<span data-ttu-id="309b6-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="309b6-193">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-193">Int32</span></span>|
|<span data-ttu-id="309b6-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-195">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-195">Int32</span></span>|
|<span data-ttu-id="309b6-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-196">IS_NULLABLE</span></span>|<span data-ttu-id="309b6-197">String</span><span class="sxs-lookup"><span data-stu-id="309b6-197">String</span></span>|
|<span data-ttu-id="309b6-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="309b6-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="309b6-199">String</span><span class="sxs-lookup"><span data-stu-id="309b6-199">String</span></span>|
|<span data-ttu-id="309b6-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="309b6-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="309b6-201">String</span><span class="sxs-lookup"><span data-stu-id="309b6-201">String</span></span>|
|<span data-ttu-id="309b6-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="309b6-203">Byte</span><span class="sxs-lookup"><span data-stu-id="309b6-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="309b6-204">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="309b6-204">Procedures</span></span>

|<span data-ttu-id="309b6-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-205">ColumnName</span></span>|<span data-ttu-id="309b6-206">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="309b6-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="309b6-208">String</span><span class="sxs-lookup"><span data-stu-id="309b6-208">String</span></span>|
|<span data-ttu-id="309b6-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309b6-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="309b6-210">String</span><span class="sxs-lookup"><span data-stu-id="309b6-210">String</span></span>|
|<span data-ttu-id="309b6-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="309b6-212">String</span><span class="sxs-lookup"><span data-stu-id="309b6-212">String</span></span>|
|<span data-ttu-id="309b6-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309b6-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="309b6-214">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-214">Int32</span></span>|
|<span data-ttu-id="309b6-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309b6-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="309b6-216">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-216">Int32</span></span>|
|<span data-ttu-id="309b6-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="309b6-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="309b6-218">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-218">Int32</span></span>|
|<span data-ttu-id="309b6-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-219">REMARKS</span></span>|<span data-ttu-id="309b6-220">String</span><span class="sxs-lookup"><span data-stu-id="309b6-220">String</span></span>|
|<span data-ttu-id="309b6-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="309b6-222">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="309b6-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309b6-223">ProcedureColumns</span></span>

|<span data-ttu-id="309b6-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-224">ColumnName</span></span>|<span data-ttu-id="309b6-225">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="309b6-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="309b6-227">String</span><span class="sxs-lookup"><span data-stu-id="309b6-227">String</span></span>|
|<span data-ttu-id="309b6-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309b6-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="309b6-229">String</span><span class="sxs-lookup"><span data-stu-id="309b6-229">String</span></span>|
|<span data-ttu-id="309b6-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="309b6-231">String</span><span class="sxs-lookup"><span data-stu-id="309b6-231">String</span></span>|
|<span data-ttu-id="309b6-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-232">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-233">String</span><span class="sxs-lookup"><span data-stu-id="309b6-233">String</span></span>|
|<span data-ttu-id="309b6-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-234">COLUMN_TYPE</span></span>|<span data-ttu-id="309b6-235">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-235">Int16</span></span>|
|<span data-ttu-id="309b6-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-236">DATA_TYPE</span></span>|<span data-ttu-id="309b6-237">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-237">Int16</span></span>|
|<span data-ttu-id="309b6-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-238">TYPE_NAME</span></span>|<span data-ttu-id="309b6-239">String</span><span class="sxs-lookup"><span data-stu-id="309b6-239">String</span></span>|
|<span data-ttu-id="309b6-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="309b6-240">COLUMN_SIZE</span></span>|<span data-ttu-id="309b6-241">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-241">Int32</span></span>|
|<span data-ttu-id="309b6-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="309b6-243">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-243">Int32</span></span>|
|<span data-ttu-id="309b6-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="309b6-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="309b6-245">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-245">Int16</span></span>|
|<span data-ttu-id="309b6-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="309b6-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="309b6-247">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-247">Int16</span></span>|
|<span data-ttu-id="309b6-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-248">NULLABLE</span></span>|<span data-ttu-id="309b6-249">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-249">Int16</span></span>|
|<span data-ttu-id="309b6-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-250">REMARKS</span></span>|<span data-ttu-id="309b6-251">String</span><span class="sxs-lookup"><span data-stu-id="309b6-251">String</span></span>|
|<span data-ttu-id="309b6-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="309b6-252">COLUMN_DEF</span></span>|<span data-ttu-id="309b6-253">String</span><span class="sxs-lookup"><span data-stu-id="309b6-253">String</span></span>|
|<span data-ttu-id="309b6-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="309b6-255">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-255">Int16</span></span>|
|<span data-ttu-id="309b6-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="309b6-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="309b6-257">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-257">Int16</span></span>|
|<span data-ttu-id="309b6-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="309b6-259">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-259">Int32</span></span>|
|<span data-ttu-id="309b6-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-261">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-261">Int32</span></span>|
|<span data-ttu-id="309b6-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-262">IS_NULLABLE</span></span>|<span data-ttu-id="309b6-263">String</span><span class="sxs-lookup"><span data-stu-id="309b6-263">String</span></span>|
|<span data-ttu-id="309b6-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="309b6-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="309b6-265">String</span><span class="sxs-lookup"><span data-stu-id="309b6-265">String</span></span>|
|<span data-ttu-id="309b6-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="309b6-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="309b6-267">String</span><span class="sxs-lookup"><span data-stu-id="309b6-267">String</span></span>|
|<span data-ttu-id="309b6-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="309b6-269">Byte</span><span class="sxs-lookup"><span data-stu-id="309b6-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="309b6-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309b6-270">ProcedureParameters</span></span>

|<span data-ttu-id="309b6-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-271">ColumnName</span></span>|<span data-ttu-id="309b6-272">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="309b6-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="309b6-274">String</span><span class="sxs-lookup"><span data-stu-id="309b6-274">String</span></span>|
|<span data-ttu-id="309b6-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309b6-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="309b6-276">String</span><span class="sxs-lookup"><span data-stu-id="309b6-276">String</span></span>|
|<span data-ttu-id="309b6-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="309b6-278">String</span><span class="sxs-lookup"><span data-stu-id="309b6-278">String</span></span>|
|<span data-ttu-id="309b6-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-279">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-280">String</span><span class="sxs-lookup"><span data-stu-id="309b6-280">String</span></span>|
|<span data-ttu-id="309b6-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-281">COLUMN_TYPE</span></span>|<span data-ttu-id="309b6-282">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-282">Int16</span></span>|
|<span data-ttu-id="309b6-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-283">DATA_TYPE</span></span>|<span data-ttu-id="309b6-284">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-284">Int16</span></span>|
|<span data-ttu-id="309b6-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-285">TYPE_NAME</span></span>|<span data-ttu-id="309b6-286">String</span><span class="sxs-lookup"><span data-stu-id="309b6-286">String</span></span>|
|<span data-ttu-id="309b6-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="309b6-287">COLUMN_SIZE</span></span>|<span data-ttu-id="309b6-288">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-288">Int32</span></span>|
|<span data-ttu-id="309b6-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="309b6-290">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-290">Int32</span></span>|
|<span data-ttu-id="309b6-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="309b6-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="309b6-292">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-292">Int16</span></span>|
|<span data-ttu-id="309b6-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="309b6-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="309b6-294">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-294">Int16</span></span>|
|<span data-ttu-id="309b6-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-295">NULLABLE</span></span>|<span data-ttu-id="309b6-296">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-296">Int16</span></span>|
|<span data-ttu-id="309b6-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-297">REMARKS</span></span>|<span data-ttu-id="309b6-298">String</span><span class="sxs-lookup"><span data-stu-id="309b6-298">String</span></span>|
|<span data-ttu-id="309b6-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="309b6-299">COLUMN_DEF</span></span>|<span data-ttu-id="309b6-300">String</span><span class="sxs-lookup"><span data-stu-id="309b6-300">String</span></span>|
|<span data-ttu-id="309b6-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="309b6-302">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-302">Int16</span></span>|
|<span data-ttu-id="309b6-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="309b6-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="309b6-304">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-304">Int16</span></span>|
|<span data-ttu-id="309b6-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="309b6-306">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-306">Int32</span></span>|
|<span data-ttu-id="309b6-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-308">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-308">Int32</span></span>|
|<span data-ttu-id="309b6-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-309">IS_NULLABLE</span></span>|<span data-ttu-id="309b6-310">String</span><span class="sxs-lookup"><span data-stu-id="309b6-310">String</span></span>|
|<span data-ttu-id="309b6-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="309b6-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="309b6-312">String</span><span class="sxs-lookup"><span data-stu-id="309b6-312">String</span></span>|
|<span data-ttu-id="309b6-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="309b6-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="309b6-314">String</span><span class="sxs-lookup"><span data-stu-id="309b6-314">String</span></span>|
|<span data-ttu-id="309b6-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="309b6-316">Byte</span><span class="sxs-lookup"><span data-stu-id="309b6-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="309b6-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="309b6-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="309b6-318">Microsoft SQL Server Oracle ODBC Driver では、共通のスキーマ コレクションに加えて次のスキーマ コレクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="309b6-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="309b6-319">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="309b6-319">Tables</span></span>

- <span data-ttu-id="309b6-320">列</span><span class="sxs-lookup"><span data-stu-id="309b6-320">Columns</span></span>

- <span data-ttu-id="309b6-321">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="309b6-321">Procedures</span></span>

- <span data-ttu-id="309b6-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309b6-322">ProcedureColumns</span></span>

- <span data-ttu-id="309b6-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309b6-323">ProcedureParameters</span></span>

- <span data-ttu-id="309b6-324">Views</span><span class="sxs-lookup"><span data-stu-id="309b6-324">Views</span></span>

- <span data-ttu-id="309b6-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="309b6-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="309b6-326">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="309b6-326">Tables and Views</span></span>

|<span data-ttu-id="309b6-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-327">ColumnName</span></span>|<span data-ttu-id="309b6-328">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="309b6-330">String</span><span class="sxs-lookup"><span data-stu-id="309b6-330">String</span></span>|
|<span data-ttu-id="309b6-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309b6-331">TABLE_OWNER</span></span>|<span data-ttu-id="309b6-332">String</span><span class="sxs-lookup"><span data-stu-id="309b6-332">String</span></span>|
|<span data-ttu-id="309b6-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-333">TABLE_NAME</span></span>|<span data-ttu-id="309b6-334">String</span><span class="sxs-lookup"><span data-stu-id="309b6-334">String</span></span>|
|<span data-ttu-id="309b6-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-335">TABLE_TYPE</span></span>|<span data-ttu-id="309b6-336">String</span><span class="sxs-lookup"><span data-stu-id="309b6-336">String</span></span>|
|<span data-ttu-id="309b6-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-337">REMARKS</span></span>|<span data-ttu-id="309b6-338">String</span><span class="sxs-lookup"><span data-stu-id="309b6-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="309b6-339">列</span><span class="sxs-lookup"><span data-stu-id="309b6-339">Columns</span></span>

|<span data-ttu-id="309b6-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-340">ColumnName</span></span>|<span data-ttu-id="309b6-341">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="309b6-343">String</span><span class="sxs-lookup"><span data-stu-id="309b6-343">String</span></span>|
|<span data-ttu-id="309b6-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309b6-344">TABLE_OWNER</span></span>|<span data-ttu-id="309b6-345">String</span><span class="sxs-lookup"><span data-stu-id="309b6-345">String</span></span>|
|<span data-ttu-id="309b6-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-346">TABLE_NAME</span></span>|<span data-ttu-id="309b6-347">String</span><span class="sxs-lookup"><span data-stu-id="309b6-347">String</span></span>|
|<span data-ttu-id="309b6-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-348">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-349">String</span><span class="sxs-lookup"><span data-stu-id="309b6-349">String</span></span>|
|<span data-ttu-id="309b6-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-350">DATA_TYPE</span></span>|<span data-ttu-id="309b6-351">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-351">Int16</span></span>|
|<span data-ttu-id="309b6-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-352">TYPE_NAME</span></span>|<span data-ttu-id="309b6-353">String</span><span class="sxs-lookup"><span data-stu-id="309b6-353">String</span></span>|
|<span data-ttu-id="309b6-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="309b6-354">PRECISION</span></span>|<span data-ttu-id="309b6-355">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-355">Int32</span></span>|
|<span data-ttu-id="309b6-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-356">LENGTH</span></span>|<span data-ttu-id="309b6-357">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-357">Int32</span></span>|
|<span data-ttu-id="309b6-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="309b6-358">SCALE</span></span>|<span data-ttu-id="309b6-359">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-359">Int16</span></span>|
|<span data-ttu-id="309b6-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="309b6-360">RADIX</span></span>|<span data-ttu-id="309b6-361">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-361">Int16</span></span>|
|<span data-ttu-id="309b6-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-362">NULLABLE</span></span>|<span data-ttu-id="309b6-363">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-363">Int16</span></span>|
|<span data-ttu-id="309b6-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-364">REMARKS</span></span>|<span data-ttu-id="309b6-365">String</span><span class="sxs-lookup"><span data-stu-id="309b6-365">String</span></span>|
|<span data-ttu-id="309b6-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-367">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="309b6-368">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="309b6-368">Procedures</span></span>

|<span data-ttu-id="309b6-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-369">ColumnName</span></span>|<span data-ttu-id="309b6-370">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="309b6-372">String</span><span class="sxs-lookup"><span data-stu-id="309b6-372">String</span></span>|
|<span data-ttu-id="309b6-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309b6-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="309b6-374">String</span><span class="sxs-lookup"><span data-stu-id="309b6-374">String</span></span>|
|<span data-ttu-id="309b6-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="309b6-376">String</span><span class="sxs-lookup"><span data-stu-id="309b6-376">String</span></span>|
|<span data-ttu-id="309b6-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309b6-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="309b6-378">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-378">Int16</span></span>|
|<span data-ttu-id="309b6-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309b6-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="309b6-380">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-380">Int16</span></span>|
|<span data-ttu-id="309b6-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="309b6-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="309b6-382">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-382">Int16</span></span>|
|<span data-ttu-id="309b6-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-383">REMARKS</span></span>|<span data-ttu-id="309b6-384">String</span><span class="sxs-lookup"><span data-stu-id="309b6-384">String</span></span>|
|<span data-ttu-id="309b6-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="309b6-386">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="309b6-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309b6-387">ProcedureColumns</span></span>

|<span data-ttu-id="309b6-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-388">ColumnName</span></span>|<span data-ttu-id="309b6-389">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="309b6-391">String</span><span class="sxs-lookup"><span data-stu-id="309b6-391">String</span></span>|
|<span data-ttu-id="309b6-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309b6-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="309b6-393">String</span><span class="sxs-lookup"><span data-stu-id="309b6-393">String</span></span>|
|<span data-ttu-id="309b6-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="309b6-395">String</span><span class="sxs-lookup"><span data-stu-id="309b6-395">String</span></span>|
|<span data-ttu-id="309b6-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-396">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-397">String</span><span class="sxs-lookup"><span data-stu-id="309b6-397">String</span></span>|
|<span data-ttu-id="309b6-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-398">COLUMN_TYPE</span></span>|<span data-ttu-id="309b6-399">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-399">Int16</span></span>|
|<span data-ttu-id="309b6-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-400">DATA_TYPE</span></span>|<span data-ttu-id="309b6-401">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-401">Int16</span></span>|
|<span data-ttu-id="309b6-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-402">TYPE_NAME</span></span>|<span data-ttu-id="309b6-403">String</span><span class="sxs-lookup"><span data-stu-id="309b6-403">String</span></span>|
|<span data-ttu-id="309b6-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="309b6-404">PRECISION</span></span>|<span data-ttu-id="309b6-405">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-405">Int32</span></span>|
|<span data-ttu-id="309b6-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-406">LENGTH</span></span>|<span data-ttu-id="309b6-407">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-407">Int32</span></span>|
|<span data-ttu-id="309b6-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="309b6-408">SCALE</span></span>|<span data-ttu-id="309b6-409">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-409">Int16</span></span>|
|<span data-ttu-id="309b6-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="309b6-410">RADIX</span></span>|<span data-ttu-id="309b6-411">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-411">Int16</span></span>|
|<span data-ttu-id="309b6-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-412">NULLABLE</span></span>|<span data-ttu-id="309b6-413">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-413">Int16</span></span>|
|<span data-ttu-id="309b6-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-414">REMARKS</span></span>|<span data-ttu-id="309b6-415">String</span><span class="sxs-lookup"><span data-stu-id="309b6-415">String</span></span>|
|<span data-ttu-id="309b6-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="309b6-416">OVERLOAD</span></span>|<span data-ttu-id="309b6-417">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-417">Int32</span></span>|
|<span data-ttu-id="309b6-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-419">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="309b6-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="309b6-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="309b6-421">Microsoft Jet ODBC Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="309b6-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="309b6-422">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="309b6-422">Tables</span></span>

- <span data-ttu-id="309b6-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="309b6-423">Indexes</span></span>

- <span data-ttu-id="309b6-424">列</span><span class="sxs-lookup"><span data-stu-id="309b6-424">Columns</span></span>

- <span data-ttu-id="309b6-425">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="309b6-425">Procedures</span></span>

- <span data-ttu-id="309b6-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309b6-426">ProcedureColumns</span></span>

- <span data-ttu-id="309b6-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309b6-427">ProcedureParameters</span></span>

- <span data-ttu-id="309b6-428">Views</span><span class="sxs-lookup"><span data-stu-id="309b6-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="309b6-429">Tables と Views</span><span class="sxs-lookup"><span data-stu-id="309b6-429">Tables and Views</span></span>

|<span data-ttu-id="309b6-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-430">ColumnName</span></span>|<span data-ttu-id="309b6-431">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="309b6-433">String</span><span class="sxs-lookup"><span data-stu-id="309b6-433">String</span></span>|
|<span data-ttu-id="309b6-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309b6-434">TABLE_OWNER</span></span>|<span data-ttu-id="309b6-435">String</span><span class="sxs-lookup"><span data-stu-id="309b6-435">String</span></span>|
|<span data-ttu-id="309b6-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-436">TABLE_NAME</span></span>|<span data-ttu-id="309b6-437">String</span><span class="sxs-lookup"><span data-stu-id="309b6-437">String</span></span>|
|<span data-ttu-id="309b6-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-438">TABLE_TYPE</span></span>|<span data-ttu-id="309b6-439">String</span><span class="sxs-lookup"><span data-stu-id="309b6-439">String</span></span>|
|<span data-ttu-id="309b6-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-440">REMARKS</span></span>|<span data-ttu-id="309b6-441">String</span><span class="sxs-lookup"><span data-stu-id="309b6-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="309b6-442">列</span><span class="sxs-lookup"><span data-stu-id="309b6-442">Columns</span></span>

|<span data-ttu-id="309b6-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-443">ColumnName</span></span>|<span data-ttu-id="309b6-444">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="309b6-446">String</span><span class="sxs-lookup"><span data-stu-id="309b6-446">String</span></span>|
|<span data-ttu-id="309b6-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309b6-447">TABLE_OWNER</span></span>|<span data-ttu-id="309b6-448">String</span><span class="sxs-lookup"><span data-stu-id="309b6-448">String</span></span>|
|<span data-ttu-id="309b6-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-449">TABLE_NAME</span></span>|<span data-ttu-id="309b6-450">String</span><span class="sxs-lookup"><span data-stu-id="309b6-450">String</span></span>|
|<span data-ttu-id="309b6-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-451">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-452">String</span><span class="sxs-lookup"><span data-stu-id="309b6-452">String</span></span>|
|<span data-ttu-id="309b6-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-453">DATA_TYPE</span></span>|<span data-ttu-id="309b6-454">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-454">Int16</span></span>|
|<span data-ttu-id="309b6-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-455">TYPE_NAME</span></span>|<span data-ttu-id="309b6-456">String</span><span class="sxs-lookup"><span data-stu-id="309b6-456">String</span></span>|
|<span data-ttu-id="309b6-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="309b6-457">PRECISION</span></span>|<span data-ttu-id="309b6-458">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-458">Int32</span></span>|
|<span data-ttu-id="309b6-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-459">LENGTH</span></span>|<span data-ttu-id="309b6-460">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-460">Int32</span></span>|
|<span data-ttu-id="309b6-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="309b6-461">SCALE</span></span>|<span data-ttu-id="309b6-462">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-462">Int16</span></span>|
|<span data-ttu-id="309b6-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="309b6-463">RADIX</span></span>|<span data-ttu-id="309b6-464">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-464">Int16</span></span>|
|<span data-ttu-id="309b6-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-465">NULLABLE</span></span>|<span data-ttu-id="309b6-466">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-466">Int16</span></span>|
|<span data-ttu-id="309b6-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-467">REMARKS</span></span>|<span data-ttu-id="309b6-468">String</span><span class="sxs-lookup"><span data-stu-id="309b6-468">String</span></span>|
|<span data-ttu-id="309b6-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-470">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="309b6-471">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="309b6-471">Procedures</span></span>

|<span data-ttu-id="309b6-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-472">ColumnName</span></span>|<span data-ttu-id="309b6-473">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="309b6-475">String</span><span class="sxs-lookup"><span data-stu-id="309b6-475">String</span></span>|
|<span data-ttu-id="309b6-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309b6-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="309b6-477">String</span><span class="sxs-lookup"><span data-stu-id="309b6-477">String</span></span>|
|<span data-ttu-id="309b6-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="309b6-479">String</span><span class="sxs-lookup"><span data-stu-id="309b6-479">String</span></span>|
|<span data-ttu-id="309b6-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309b6-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="309b6-481">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-481">Int16</span></span>|
|<span data-ttu-id="309b6-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309b6-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="309b6-483">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-483">Int16</span></span>|
|<span data-ttu-id="309b6-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="309b6-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="309b6-485">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-485">Int16</span></span>|
|<span data-ttu-id="309b6-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-486">REMARKS</span></span>|<span data-ttu-id="309b6-487">String</span><span class="sxs-lookup"><span data-stu-id="309b6-487">String</span></span>|
|<span data-ttu-id="309b6-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="309b6-489">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="309b6-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309b6-490">ProcedureColumns</span></span>

|<span data-ttu-id="309b6-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-491">ColumnName</span></span>|<span data-ttu-id="309b6-492">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309b6-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="309b6-494">String</span><span class="sxs-lookup"><span data-stu-id="309b6-494">String</span></span>|
|<span data-ttu-id="309b6-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309b6-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="309b6-496">String</span><span class="sxs-lookup"><span data-stu-id="309b6-496">String</span></span>|
|<span data-ttu-id="309b6-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="309b6-498">String</span><span class="sxs-lookup"><span data-stu-id="309b6-498">String</span></span>|
|<span data-ttu-id="309b6-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-499">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-500">String</span><span class="sxs-lookup"><span data-stu-id="309b6-500">String</span></span>|
|<span data-ttu-id="309b6-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-501">COLUMN_TYPE</span></span>|<span data-ttu-id="309b6-502">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-502">Int16</span></span>|
|<span data-ttu-id="309b6-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-503">DATA_TYPE</span></span>|<span data-ttu-id="309b6-504">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-504">Int16</span></span>|
|<span data-ttu-id="309b6-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-505">TYPE_NAME</span></span>|<span data-ttu-id="309b6-506">String</span><span class="sxs-lookup"><span data-stu-id="309b6-506">String</span></span>|
|<span data-ttu-id="309b6-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="309b6-507">PRECISION</span></span>|<span data-ttu-id="309b6-508">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-508">Int32</span></span>|
|<span data-ttu-id="309b6-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-509">LENGTH</span></span>|<span data-ttu-id="309b6-510">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-510">Int32</span></span>|
|<span data-ttu-id="309b6-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="309b6-511">SCALE</span></span>|<span data-ttu-id="309b6-512">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-512">Int16</span></span>|
|<span data-ttu-id="309b6-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="309b6-513">RADIX</span></span>|<span data-ttu-id="309b6-514">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-514">Int16</span></span>|
|<span data-ttu-id="309b6-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-515">NULLABLE</span></span>|<span data-ttu-id="309b6-516">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-516">Int16</span></span>|
|<span data-ttu-id="309b6-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-517">REMARKS</span></span>|<span data-ttu-id="309b6-518">String</span><span class="sxs-lookup"><span data-stu-id="309b6-518">String</span></span>|
|<span data-ttu-id="309b6-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="309b6-519">OVERLOAD</span></span>|<span data-ttu-id="309b6-520">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-520">Int32</span></span>|
|<span data-ttu-id="309b6-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-522">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="309b6-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309b6-523">ProcedureParameters</span></span>

|<span data-ttu-id="309b6-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="309b6-524">ColumnName</span></span>|<span data-ttu-id="309b6-525">DataType</span><span class="sxs-lookup"><span data-stu-id="309b6-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="309b6-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="309b6-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="309b6-527">String</span><span class="sxs-lookup"><span data-stu-id="309b6-527">String</span></span>|
|<span data-ttu-id="309b6-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309b6-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="309b6-529">String</span><span class="sxs-lookup"><span data-stu-id="309b6-529">String</span></span>|
|<span data-ttu-id="309b6-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="309b6-531">String</span><span class="sxs-lookup"><span data-stu-id="309b6-531">String</span></span>|
|<span data-ttu-id="309b6-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-532">COLUMN_NAME</span></span>|<span data-ttu-id="309b6-533">String</span><span class="sxs-lookup"><span data-stu-id="309b6-533">String</span></span>|
|<span data-ttu-id="309b6-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-534">COLUMN_TYPE</span></span>|<span data-ttu-id="309b6-535">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-535">Int16</span></span>|
|<span data-ttu-id="309b6-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-536">DATA_TYPE</span></span>|<span data-ttu-id="309b6-537">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-537">Int16</span></span>|
|<span data-ttu-id="309b6-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309b6-538">TYPE_NAME</span></span>|<span data-ttu-id="309b6-539">String</span><span class="sxs-lookup"><span data-stu-id="309b6-539">String</span></span>|
|<span data-ttu-id="309b6-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="309b6-540">COLUMN_SIZE</span></span>|<span data-ttu-id="309b6-541">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-541">Int32</span></span>|
|<span data-ttu-id="309b6-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="309b6-543">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-543">Int32</span></span>|
|<span data-ttu-id="309b6-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="309b6-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="309b6-545">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-545">Int16</span></span>|
|<span data-ttu-id="309b6-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="309b6-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="309b6-547">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-547">Int16</span></span>|
|<span data-ttu-id="309b6-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-548">NULLABLE</span></span>|<span data-ttu-id="309b6-549">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-549">Int16</span></span>|
|<span data-ttu-id="309b6-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309b6-550">REMARKS</span></span>|<span data-ttu-id="309b6-551">String</span><span class="sxs-lookup"><span data-stu-id="309b6-551">String</span></span>|
|<span data-ttu-id="309b6-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="309b6-552">COLUMN_DEF</span></span>|<span data-ttu-id="309b6-553">String</span><span class="sxs-lookup"><span data-stu-id="309b6-553">String</span></span>|
|<span data-ttu-id="309b6-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309b6-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="309b6-555">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-555">Int16</span></span>|
|<span data-ttu-id="309b6-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="309b6-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="309b6-557">Int16</span><span class="sxs-lookup"><span data-stu-id="309b6-557">Int16</span></span>|
|<span data-ttu-id="309b6-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309b6-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="309b6-559">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-559">Int32</span></span>|
|<span data-ttu-id="309b6-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309b6-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="309b6-561">Int32</span><span class="sxs-lookup"><span data-stu-id="309b6-561">Int32</span></span>|
|<span data-ttu-id="309b6-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309b6-562">IS_NULLABLE</span></span>|<span data-ttu-id="309b6-563">String</span><span class="sxs-lookup"><span data-stu-id="309b6-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="309b6-564">関連項目</span><span class="sxs-lookup"><span data-stu-id="309b6-564">See also</span></span>

- [<span data-ttu-id="309b6-565">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="309b6-565">ADO.NET Overview</span></span>](ado-net-overview.md)
